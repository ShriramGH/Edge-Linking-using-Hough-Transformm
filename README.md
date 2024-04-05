# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program 

### Developed by : Shriram S
### Reg.No. 212222240098

### Image Processing

```py
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("Ex-7.jpg",0)
img_c=cv2.imread("Ex-7.jpg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)

```

```py
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
```
```py
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Canny Edge Detection

```py
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Hough Transform

```py
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```


## Output

### Input image and grayscale image

![image](https://github.com/ShriramGH/Edge-Linking-using-Hough-Transformm/assets/117991122/324db447-69cb-4b8c-b623-f0a6711541ad)

### Canny Edge detector output


![image](https://github.com/ShriramGH/Edge-Linking-using-Hough-Transformm/assets/117991122/0f70c77c-7906-44d7-8271-9899bd4de7a7)


### Display the result of Hough transform

![image](https://github.com/ShriramGH/Edge-Linking-using-Hough-Transformm/assets/117991122/99d5fdc9-7034-4102-9964-22cbb9b30ae1)

## Result:

### Thus the program is written with python and OpenCV to detect lines using Hough transform.
