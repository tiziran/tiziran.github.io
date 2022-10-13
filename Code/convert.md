---
updated: 2022-09-20T07:29:02+02:00
created: 2022-08-10T22:35:21+02:00
tags: i/convert, i/python, i/c , i/matlab
GA: G-SFK3F1H705
---
top: [[010_Guide]]
top: [[020 MOC code]]

Python:
```py
x = 8
se = cv2.getStructuringElement(cv2.MORPH_ELLIPSE, (2*x-1, 2*x-1))
```

C++:
```cpp
#incluse  <opencv.hpp>
int x=8;
cv::Mat se = cv::getStructuringElement(cv::MorphShapes::MORPH_ELLIPSE, cv::Size(2*x-1, 2*x-1));
```

Matlab:
```matlab
dst = imerode(src,se);
```

