---
updated: 2022-09-20T07:29:04+02:00
created: 2022-08-10T22:33:37+02:00
tags: i/convert, i/python, i/c , i/matlab
GA: G-SFK3F1H705

---
top: [[010_Guide]]
top: [[020 MOC code]]

Python:
```py
x = 8
se = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, (2*x-1, 2*x-1))
dst = cv2.morphologyEx(src, cv2.MORPH_CLOSE, se)
```

C++:
```cpp
#incluse  <opencv.hpp>
int x=8;
cv::Mat se = cv::getStructuringElement(cv::MorphShapes::MORPH_ELLIPSE, cv::Size(2*x-1, 2*x-1));

cv::erode(src, dst, se);

```

Matlab:
```matlab
x=8
se = strel('disk',2*x-1);

dst = imerode(src,se);

```


