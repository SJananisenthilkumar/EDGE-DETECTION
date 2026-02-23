# EDGE-DETECTION
# NAME : JANANI S
# REG NO : 212223230086
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.


## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('leaf.jpeg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

sobelx  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 1, dy = 0, ksize = 3) 
sobely  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 0, dy = 1, ksize = 3)

sobelx = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)  # Sobel X
sobely = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3)  # Sobel Y
sobel_combined = cv2.magnitude(sobelx, sobely) 

plt.figure(figsize = (12, 16))
plt.subplot(321); plt.axis('on'); plt.imshow(image[:,:,::-1]); plt.title('Original')
plt.subplot(322); plt.axis('on'); plt.imshow(gray_image, cmap='gray');plt.title('Grayscale') 
plt.subplot(323); plt.axis('on'); plt.imshow(sobelx);plt.title('Sobel-X Edge Map')
plt.subplot(324); plt.axis('on'); plt.imshow(sobely);plt.title('Sobel-Y Edge Map')

plt.figure(figsize = (12, 16))
plt.axis('off'); plt.imshow(sobel_combined, cmap='gray' ); plt.title('sobel_combined ')

```
## Output:
### SOBEL EDGE DETECTOR & LAPLACIAN EDGE DETECTOR:

<img width="1161" height="401" alt="image" src="https://github.com/user-attachments/assets/9d687630-7361-4415-b946-aaa456b00cef" />



### CANNY EDGE DETECTOR

<img width="1181" height="396" alt="image" src="https://github.com/user-attachments/assets/135bdc95-effb-4db0-8bf6-9662e02a8040" />

<img width="1117" height="643" alt="image" src="https://github.com/user-attachments/assets/94bd4728-d0a6-42b0-89bd-84e5a5e8c36b" />


## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
