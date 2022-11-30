---
updated: 2022-11-30T15:24:24+01:00
created: 2022-08-10T22:33:37+02:00
tags: i/convert, i/python, i/c , i/matlab
GA: G-SFK3F1H705

---
top: [[010_Guide]]
top: [[020 MOC code]]

remove background or minimum form image. help to remove noise or background from detection specially for the contour 

Python:
```py

im = im - im.min()

```

C++:
```cpp
#incluse  <opencv.hpp>
double min1, max1;
cv::minMaxLoc(Mat_im, &min1, &max1);
    for (int y = 0; y < Mat_im.rows; y++)
        for (int x = 0; x < Mat_im.cols; x++)
            Mat_im.at<uchar>(y, x) = saturate_cast<uchar>(Mat_im.at<uchar>(y, x) - min1);
```

Matlab:
```matlab


```


