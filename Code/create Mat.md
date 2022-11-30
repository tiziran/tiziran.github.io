---
updated: 2022-11-30T15:22:40+01:00
created: 2022-08-10T22:35:21+02:00
tags: i/convert, i/python, i/c , i/matlab
GA: G-SFK3F1H705
---
top: [[010_Guide]]
top: [[020 MOC code]]

Python:
```py

bin_im = bin_im.astype(np.uint8)*255

```

C++:
``` cpp
#incluse  <opencv.hpp>
//data will be copied
cv::Mat(sample);
cv::Mat histogram(1, 255, CV_8U, Scalar(0));
cv::Mat histogram2= cv::Mat::zeros(histogram.size(), CV_32F);
cv::Mat bin_im;
cv::Mat image_elip = img_out.clone();    

//create reference
cv::Mat(sample, false);


_src.getMat()
image_elip.convertTo(image_elip, CV_8U);
CV_Assert(hist.type() == CV_32F);
```

Matlab:
```matlab

```

example: 
```cpp

```

