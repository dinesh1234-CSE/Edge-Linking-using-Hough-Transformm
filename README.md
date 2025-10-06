# Edge-Linking-using-Hough-Transformm
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
## PROGRAM
Developed by : CH.V.S.DINESH KUMAR
Register no:212224040055
## Image Processing
```PY
import numpy as np
import cv2
import matplotlib.pyplot as plt

img=cv2.imread("/content/CHESS",0)
img_c=cv2.imread("/content/CHESS",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
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
## Canny Edge Detection
```py
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
## Hough Transform
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

<img width="1027" height="500" alt="download" src="https://github.com/user-attachments/assets/9ae594f8-3e78-4525-b7a7-a014ea80339e" />


### Canny Edge detector output

<img width="389" height="411" alt="download" src="https://github.com/user-attachments/assets/550f8c3c-cfa1-4be2-b456-7f950a29447a" />


### Display the result of Hough transform

<img width="389" height="411" alt="download" src="https://github.com/user-attachments/assets/2b219b45-e224-4818-8da4-097d3fab24f4" />


## RESULT:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
