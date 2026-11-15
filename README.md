# EXP-3-Record-Histogram-processing

## Aim:
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

## Software Used:

Anaconda – Python 3.7                   
Jupyter Notebook / VS Code  
OpenCV (cv2)  
NumPy  
Matplotlib  

## Algorithm:
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the image parrot.jpg in grayscale format.

Step 3:
Display the grayscale image and plot its histogram.

Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6:
Read the same image in color format.

Step 7:
Split the image into B, G, R channels and plot their histograms.

Step 8:
Convert the image from BGR to HSV color space.

Step 9:
Apply histogram equalization on the V (Value) channel.

Step 10:
Merge the channels and convert the image back to BGR format.

Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.


## Program:
### Developed By:
### Name: FRANKLIN F

### Register No: 212224240041
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('MY_PIC.jpeg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('MY_PIC.jpeg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')


```

## Output:
### Grayscale Histogram Equalization:

#### Original grayscale image is displayed

<img width="452" height="542" alt="image" src="https://github.com/user-attachments/assets/cf977d35-db4d-4e08-9c5d-a6dfe9092b57" />


#### Histogram of original grayscale image is plotted
<img width="842" height="547" alt="image" src="https://github.com/user-attachments/assets/98c79bff-50e3-4617-99f2-523c9e95e443" />


#### Enhanced image after histogram equalization is displayed
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/c96f100c-7933-4648-8d91-4c3a2d91bac9" />

#### Histogram of enhanced grayscale image shows improved contrast
<img width="452" height="542" alt="image" src="https://github.com/user-attachments/assets/cf977d35-db4d-4e08-9c5d-a6dfe9092b57" />

### Color Image Histogram Equalization:

#### Original color image is displayed

<img width="480" height="540" alt="image" src="https://github.com/user-attachments/assets/0a455917-c221-4554-8e7a-b6b12bf04e5e" />


#### Histogram of B, G, R channels is plotted
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/0e3c4584-17d5-4ec6-98bc-6ae9b3d10fcb" />

#### Enhanced image after HSV-based equalization is displayed

<img width="1392" height="483" alt="image" src="https://github.com/user-attachments/assets/a05190f7-af93-4abf-88dc-e68adcb1a0f6" />


#### Histogram of enhanced image shows better intensity distribution

<img width="1237" height="372" alt="download" src="https://github.com/user-attachments/assets/6d18ad7b-81b8-4836-a0fc-df83df1867dd" />


## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
