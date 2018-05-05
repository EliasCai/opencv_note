
1. cv2.cvtColor：改变颜色空间
- [参考](https://docs.opencv.org/3.0.0/df/d9d/tutorial_py_colorspaces.html)
2. cv2.threshold：阈值函数，如果像素值大于阈值，则它被分配一个值（可以是白色），否则它被分配另一个值（可能是黑色）。
- 参数：四个参数，第一个参数是源图像，它应该是灰度图像。第二个参数是用于对像素值进行分类的阈值。第三个参数是MaxVar，它表示如果像素值大于（有时小于）阈值，则要给出的值。第四个参数Opencv提供了不同的阈值类型
- 输出：img对象
- [参考](https://docs.opencv.org/3.4/d7/d4d/tutorial_py_thresholding.html)
3. cv2.findContours：寻找轮廓函数
- 参数：三个参数，一是img对象，二是轮廓搜索模式，三是轮廓逼近方式
- 输出：轮廓的列表和层次结构
- [参考](https://docs.opencv.org/3.1.0/d4/d73/tutorial_py_contours_begin.html)
    ```
	import numpy as np
	import cv2

	im = cv2.imread('test.jpg')
	imgray = cv2.cvtColor(im,cv2.COLOR_BGR2GRAY)
	ret,thresh = cv2.threshold(imgray,127,255,0)
	im2, contours, hierarchy = cv2.findContours(thresh,cv2.RETR_TREE,cv2.CHAIN_APPROX_SIMPLE)
	```
4. cv2.getStructuringElement：形态转换
- [参考](https://docs.opencv.org/3.0-beta/doc/py_tutorials/py_imgproc/py_morphological_ops/py_morphological_ops.html)

5. cv2.canny 边缘检测
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/detect01.PNG" style="width:400px;">
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/detect02.PNG" style="width:400px;">
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/canny01.PNG" alt="drawing" style="width: 400px;"/>
- <img src="https://raw.githubusercontent.com/EliasCai/opencv_note/master/images/canny02.PNG" alt="drawing" style="width: 400px;"/>
