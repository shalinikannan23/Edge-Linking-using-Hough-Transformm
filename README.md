# EX 07 -Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1: Import all the necessary modules for the program.
### Step2: Load a image using imread() from cv2 module.
### Step3: Convert the image to grayscale.
### Step4: Using Canny operator from cv2,detect the edges of the image.
### Step5: Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## PROGRAM:
## DEVELOPED BY: SHALINI K
## REGISTER NUMBER: 212222240095
## Read image and convert it to grayscale image

```py
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("animal.jpg",0)
img_c=cv2.imread("animal.jpg",1)
img=cv2.resize(img,(200,200))
img_c=cv2.resize(img_c,(200,200))
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
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
## OUTPUT:
<img height=16% width=24% src="https://github.com/shalinikannan23/Edge-Linking-using-Hough-Transformm/assets/118656529/50102cfa-cf67-4cc1-8e9a-e200f98b1284">

## Find the edges in the image using canny detector and display:
```py
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
## OUTPUT:
<img height=16% width=24% src="https://github.com/shalinikannan23/Edge-Linking-using-Hough-Transformm/assets/118656529/b1677670-9641-4306-894d-193bb249ffa0">

## Detect points that form a line using HoughLinesP:
```PY
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
## Draw lines on the image:
```PY
for line in lines:
  x1,y1,x2,y2=line[0]
  cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
## Display the result:
```PY
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## OUTPUT:

<img height=16% width=24% src="https://github.com/shalinikannan23/Edge-Linking-using-Hough-Transformm/assets/118656529/10e97ed2-1840-4667-a4a0-6cd4eeb178dd">

## RESULT:

Thus the program is written with python and OpenCV to detect lines using Hough transform.
