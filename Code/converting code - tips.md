---
tags: i/tips, i/convert 
GA: G-SFK3F1H705
main: [[010_Guide]]
link: 
created: 2022-08-20T13:22:13+02:00
updated: 2022-09-20T07:32:26+02:00
---




How to convert programming languages: Matlab/Python/C/C++ and modern C++ 23

1.  trace the images: what happens to each image and memory and copy and transit to that image
	1. Using a table and each column transitions for each image 	
	2. always check the call by reference or call by value	
	3. check the naming similarity    
2.  compare the output of each step: store data, matrix, array, and vector to the text file and compare compliantly also compare the differences because in image processing some times not exactly output same and different version of OpenCV also has different result
	1. the version of the library 
	2. the function use which library
	3. the input/output of the function and call by reference or call by value    
3.  The same function in Matlab, Python, C++, and OpenCV is different even change OS also make difference in output    
4. test ... test ... line by line
5. initialization 
	1. very important. some times the code does not run because of that. good to know the output type in advanced. 
```py
Mat img_gradient_cornerHarris = Mat::zeros(sourceImage.size(), CV_32FC1);
        cornerHarris(img_gradient, img_gradient_cornerHarris, blockSize, apertureSize, k);
```
in the code above the program does not run without initialization. the output also known as float . 
```py
Mat img_gradient=Mat::zeros(sourceImage.size(), CV_32FC1);;
        cv::morphologyEx(sourceImage, img_gradient, cv::MORPH_GRADIENT, se);
```
