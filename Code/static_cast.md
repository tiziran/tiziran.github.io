---
updated: 2022-08-29T15:29:55+02:00
created: 2022-08-10T22:35:21+02:00
tags: i/convert, i/python, i/c , i/matlab
GA: G-SFK3F1H705
---
top: [[010_Guide]]
top: [[020 MOC code]]

saturate in the name means that when the input value v is out of the range of the target type, the result is not formed just by taking low bits of the input, but instead the value is clipped.

Python:
```py

```

C++:
```cpp
#incluse  <opencv.hpp>

static_cast

```

Matlab:
```matlab

```

example: 


```cpp

uchar a = saturate_cast<uchar>(-100); // a = 0 (UCHAR_MIN)
short b = saturate_cast<short>(33333.33333); // b = 32767 (SHRT_MAX)



saturate_cast<float>
 
buf.at<Vec3b>(i) = Vec3b(saturate_cast<uchar>(i*180./hsize), 255, 255);
```

