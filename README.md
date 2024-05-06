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
# Program:
```
Developed By: VAISHNAVI S
Register No: 212222230165
```
```
# Read image and convert it to grayscale image
import cv2
import numpy as np
r=cv2.imread('catt.jpg',-1)
gray=cv2.cvtColor(r,cv2.COLOR_BGR2GRAY)
img = cv2.GaussianBlur(gray,(3,3),0)
cv2.imshow('origianl',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imshow('gray',gray)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Find the edges in the image using canny detector and display
canny_edges = cv2.Canny(img, 50, 120)
cv2.imshow('canny',canny_edges)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Detect points that form a line using HoughLinesP
lines =cv2.HoughLinesP(canny_edges, 1, np.pi/180,threshold = 15, minLineLength =5 ,
maxLineGap = 7)



# Draw lines on the image
for line in lines:
 x1,y1,x2,y2 = line[0]
 cv2.line(r, (x1,y1),(x2,y2),(255,0,0),3)



# Display the result
cv2.imshow('hough_detected',r)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output

### Input image and grayscale image
![272628313-439083fb-e2a7-40b9-ae23-c2168c8e8440](https://github.com/Vaishnavi-saravanan/Edge-Linking-using-Hough-Transformm/assets/118541897/2033b716-b692-443a-9dfe-3820c3e0e481)


### Canny Edge detector output
![272628291-ec7e0880-d7fa-446b-ae52-7e7e0bce53c0](https://github.com/Vaishnavi-saravanan/Edge-Linking-using-Hough-Transformm/assets/118541897/ec3a5f69-455a-4851-9a75-ed94b18983b9)

# Display the result of the Hough transform
![Uploading 272628305-5744c6ec-2e49-4f6a-aeb8-6d66e47b3931.png…]()

# Result:
Thus the program is written with Python and OpenCV to detect lines using Hough transform.

