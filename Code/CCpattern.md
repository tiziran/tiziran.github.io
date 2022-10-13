---
updated: 2022-10-13T13:05:35+02:00
created: 2022-08-10T22:32:18+02:00
tags: i/c
GA: G-SFK3F1H705
---
top: [[010_Guide]]
top: [[020 MOC code]]

using 4 pattern for CC in order to detect position/angle/rotation of the pattern because some of the OpenCV functions works only for the 4 points at least

```py

```
findHomography it must at least 4 points
```cpp
#incluse  <opencv.hpp>
std::vector<cv::Point2f> srcPoints2;
    srcPoints2.push_back(cv::Point2f(-0.5, 0.5));
    srcPoints2.push_back(cv::Point2f(0.5, -0.5));
    srcPoints2.push_back(cv::Point2f(1.5, 2.5));
    srcPoints2.push_back(cv::Point2f(0.0, 0.0));
std::vector<cv::Point2f> dstPoints2;
    dstPoints2.push_back(cv::Point2f(222, 111));
    dstPoints2.push_back(cv::Point2f(333, 222));
    dstPoints2.push_back(cv::Point2f(444, 333));
    dstPoints2.push_back(cv::Point2f(555, 444));
Mat H = findHomography( srcPoints2, dstPoints2 );
cout << "H:\n" << H << endl;

```
output: 3 * 3
```
H:
[-16948.59122860285, -19834.59122860288, 555.0000000000035;
 -12961.19342145214, -14737.19342145216, 444.0000000000019;
 -35.92250276712353, -45.92250276712362, 1]
```


getAffineTransform can be 3 points for each image, 
```cpp
#incluse  <opencv.hpp>
Point2f srcTri[3];
    srcTri[0] = Point2f(-0.5, 0.5);
    srcTri[1] = Point2f(0.5, -0.5);
    srcTri[2] = Point2f(1.5, 2.5);
Point2f dstTri[3];
    dstTri[0] = Point2f(111.0, 444.0);
    dstTri[1] = Point2f(222.0, 111.0);
    dstTri[2] = Point2f(333.0, 222.0);
Mat transf = cv::getAffineTransform(srcTri, dstTri);
cout << "transf:\n" << transf << endl;

```
output: 3 * 2
```
transf:
[111, 1.06581410364015e-14, 166.5;
 -222, 111, 277.5]
```


computeAffine function: can get 3 points 
```cpp
#incluse  <opencv.hpp>
static bool computeAffine(const vector<Point2d>& srcPoints, const vector<Point2d>& dstPoints, Mat& transf)
{
    // sanity check
    if ((srcPoints.size() < 3) || (srcPoints.size() != dstPoints.size()))
        return false;

    // container for output
    transf.create(2, 3, CV_64F);

    // fill the matrices
    const int n = (int)srcPoints.size(), m = 3;
    Mat A(n, m, CV_64F), xc(n, 1, CV_64F), yc(n, 1, CV_64F);
    for (int i = 0; i < n; i++)
    {
        double x = srcPoints[i].x, y = srcPoints[i].y;
        double rowI[m] = { x, y, 1 };
        Mat(1, m, CV_64F, rowI).copyTo(A.row(i));
        xc.at<double>(i, 0) = dstPoints[i].x;
        yc.at<double>(i, 0) = dstPoints[i].y;
    }

    // solve linear equations (for x and for y)
    Mat aTa, resX, resY;
    mulTransposed(A, aTa, true);
    solve(aTa, A.t() * xc, resX, DECOMP_CHOLESKY);
    solve(aTa, A.t() * yc, resY, DECOMP_CHOLESKY);

    // store result
    memcpy(transf.ptr<double>(0), resX.data, m * sizeof(double));
    memcpy(transf.ptr<double>(1), resY.data, m * sizeof(double));

    return true;
}
int main() {    
    vector<Point2d> srcPoints {
            { -0.5, 0.5},
            {0.5, -0.5},
            {1.5, 2.5}
    };
    vector<Point2d> dstPoints{
           { 111.0,222.0},
              {333.0,333.0},
              {444.0,111.0}
    };
	Mat transf;
    computeAffine(srcPoints, dstPoints, transf);
    cout << "transf:\n" << transf << endl;
}
```
output : 3 * 2
```
transf:
[194.25, -27.75, 222;
 27.75, -83.25, 277.5]
```


cv::perspectiveTransform only worked on point2d, it must 3 * 3 transfer matrix
```cpp
vector<Point2d> inputVector{ {0,0} };
vector<Point2d> emptyOutputVector;
cv::perspectiveTransform(inputVector, emptyOutputVector, transf2);
std::cout << "transformed_pts 0 , 0:\n" << emptyOutputVector << std::endl;
```

