---
updated: 2022-09-05T16:36:36+02:00
created: 2022-08-10T22:33:37+02:00
tags: i/convert, i/python, i/c , i/matlab
GA: G-SFK3F1H705

---
top: [[010_Guide]]
top: [[020 MOC code]]



Python:
```py

contours, hierarchy = cv2.findContours(opening, cv2.RETR_LIST, cv2.CHAIN_APPROX_SIMPLE)

```

C++:
```cpp
#incluse  <opencv.hpp>
vector<vector<Point> > contours;
vector<Vec4i> hierarchy;
findContours(opening, contours, hierarchy, RETR_TREE, CHAIN_APPROX_SIMPLE);
```

Matlab:
```matlab


```


# Example 
```cpp
vector<RotatedRect> minEllipse(contours.size());
    for (size_t i = 0; i < contours.size(); i++)
    {     
        if (contours[i].size() > 5)
        {            
            for (int j = 0; j < contours[i].size(); j++)
            {
                //cv::Point2d p = contours[i][j];
                //int va = src.at<uchar>(p);              
                minEllipse[i] = fitEllipse(contours[i]);                            
            }            
        }
    }
```