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

# Read Original Grayscale Image
img = cv2.imread(
    'WhatsApp Image 2026-10-24 at 3.32.56 PM.jpeg',
    cv2.IMREAD_GRAYSCALE
)

if img is None:
    raise ValueError("Image not found. Check the image path.")

# Display Original Image
plt.figure(figsize=(6, 5))
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')
plt.show()

# Display Original Histogram
plt.hist(img.ravel(), bins=256, range=[0, 256])
plt.title('Original Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()

# Perform Histogram Equalization
img_eq = cv2.equalizeHist(img)

# Display Equalized Histogram
plt.hist(img_eq.ravel(), bins=256, range=[0, 256])
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()

# Display Equalized Image
plt.figure(figsize=(6, 5))
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.axis('off')
plt.show()

# Read Original Color Image
img = cv2.imread(
    'WhatsApp Image 2026-10-24 at 3.32.56 PM.jpeg',
    cv2.IMREAD_COLOR
)

if img is None:
    raise ValueError("Color image not found.")

# Convert BGR to HSV
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Apply Histogram Equalization to V Channel
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Convert HSV to BGR
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Display Equalized Color Image
plt.imshow(cv2.cvtColor(img_eq, cv2.COLOR_BGR2RGB))
plt.title('Equalized Image')
plt.axis('off')
plt.show()

# Display Color Image Histogram
plt.hist(img_eq.ravel(), bins=256, range=[0, 256])
plt.title('Histogram Equalized')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()

# Compare Original and Equalized Color Images
plt.figure(figsize=(20, 10))

plt.subplot(221)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('off')

plt.subplot(222)
plt.imshow(cv2.cvtColor(img_eq, cv2.COLOR_BGR2RGB))
plt.title('Equalized Image')
plt.axis('off')

plt.show()

# Compare Original and Equalized Histograms
plt.figure(figsize=(15, 4))

plt.subplot(121)
plt.hist(img.ravel(), bins=256, range=[0, 256])
plt.title('Original Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.subplot(122)
plt.hist(img_eq.ravel(), bins=256, range=[0, 256])
plt.title('Histogram Equalized')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')

plt.tight_layout()
plt.show()



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
