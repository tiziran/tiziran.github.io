---
updated: 2022-09-05T16:26:52+02:00
created: 2022-08-10T22:33:37+02:00
tags: i/convert, i/python, i/c , i/matlab
GA: G-SFK3F1H705

---
top: [[010_Guide]]
top: [[020 MOC code]]

calculate time spend for your method by using C++ or OpenCV function. 

Python:
```py

e1 = cv2.getTickCount()
######    
e2 = cv2.getTickCount()
time = (e2 - e1)/ cv2.getTickFrequency()

```

C++:
```cpp
// OpenCV
#incluse  <opencv.hpp>
	double t = (double)getTickCount(); 
	// do something ... 
	t = ((double)getTickCount() - t)/getTickFrequency(); 
	std::cout << "Times passed in seconds: " << t << std::endl;

// C++
#include <time.h>
	clock_t start, end;
	double elapsed;
	start = clock();    
	/* Your code    */    
	end = clock();
	elapsed = ((double) (end - start)) / CLOCKS_PER_SEC;
	std::cout<<elapsed;
```

Matlab:
```matlab


```


