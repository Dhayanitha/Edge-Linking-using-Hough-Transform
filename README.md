# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image
### Step2:
Find the edges in the image using canny detector and display
### Step3:
Detect points that form a line using HoughLinesP
### Step4:
Draw lines on the image
### Step5:
Display the result

# Program:
## Developed By : H.Dhayanitha
## Register Number: 212220230010

# Read image and convert it to grayscale image
```
import cv2 
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("br.jpg",0)
img_c=cv2.imread("br.jpg",1)
img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Gray Image')
plt.imshow(img)
plt.show()
# Find the edges in the image using canny detector and display
canny=cv2.Canny(img,120,150)
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Canny')
plt.imshow(canny)
plt.show()
```
# Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,50,20,2)
```
# Draw lines on the image
```
blank_image = np.ones(img.shape, dtype=np.uint8)
for lin in lines:
    x1,y1,x2,y2=lin[0]
    cv2.line(blank_image,(x1,y1),(x2,y2),(255,0,0),2)
``` 
# Display the result
```
plt.figure(figsize=(20,20))
plt.subplot(1,2,1)
plt.axis("off")
plt.title('Original image')
plt.imshow(img_c)
plt.subplot(1,2,2)
plt.axis("off")
plt.title('Hough Transform')
plt.imshow(blank_image)
plt.show()
```
## Output

### Input image and grayscale image

![d1](https://user-images.githubusercontent.com/75235032/169099515-90c7079e-903e-4879-a08d-487bbfdf6c59.jpg)

### Canny Edge detector output

![d2](https://user-images.githubusercontent.com/75235032/169099537-40f3cee7-cf62-4391-bf6f-1e287e71047c.jpg)

### Display the result of Hough transform

![d3](https://user-images.githubusercontent.com/75235032/169099581-4b977f79-f5ed-4a3c-873d-85439743ed9c.jpg)

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
