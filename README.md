# EXPERIMENT 03 – HISTOGRAM EQUALIZATION USING OPENCV
# PROGRAM DEVELOPED BY
# Name:FRANKLIN .F
# Register No.: 212224240041

## AIM

To implement histogram equalization using OpenCV in Python to improve the contrast of an image by adjusting its intensity distribution.

## SOFTWARE REQUIRED

- Anaconda Python 3.7
- Jupyter Notebook
- OpenCV
- NumPy
- Matplotlib

## ALGORITHM

1. Import the required libraries such as OpenCV, NumPy and Matplotlib.
2. Read the input image using `cv2.imread()`.
3. Convert the color image into a grayscale image using `cv2.cvtColor()`.
4. Display the original grayscale image.
5. Calculate the histogram of the original image using `cv2.calcHist()`.
6. Apply histogram equalization using `cv2.equalizeHist()`.
7. Calculate the histogram of the equalized image.
8. Display the original image, equalized image and their histograms.
9. Compare both images to observe the improvement in contrast.


## PROGRAM
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('Ip2.jpg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

hist_original = cv2.calcHist([gray_image], [0], None, [256], [0, 256])

equalized_image = cv2.equalizeHist(gray_image)

hist_equalized = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])

plt.figure(figsize=(10, 7))

plt.subplot(2, 2, 1)
plt.imshow(gray_image, cmap='gray')
plt.title('Original Grayscale Image')
plt.axis('off')

plt.subplot(2, 2, 2)
plt.imshow(equalized_image, cmap='gray')
plt.title('Equalized Image')
plt.axis('off')

plt.subplot(2, 2, 3)
plt.plot(hist_original, color='black')
plt.title('Original Histogram')
plt.xlim([0, 256])

plt.subplot(2, 2, 4)
plt.plot(hist_equalized, color='black')
plt.title('Equalized Histogram')
plt.xlim([0, 256])

plt.tight_layout()
plt.show()
```

## OUTPUT
## Input Grayscale Image and Color Image
## Histogram of Grayscale Image and any channel of Color Image
<img width="431" height="422" alt="image" src="https://github.com/user-attachments/assets/175ebbcc-48f5-488e-971f-c7599364729d" />
<img width="605" height="443" alt="image" src="https://github.com/user-attachments/assets/5acc314d-b795-425b-8751-d8ae4dbcb9df" />

## Histogram Equalization of Grayscale Image
<img width="357" height="425" alt="image" src="https://github.com/user-attachments/assets/a9a105e3-fd0c-4f3d-8a44-48e934685979" />
<img width="667" height="428" alt="image" src="https://github.com/user-attachments/assets/d5dfd995-3090-4397-8ad8-93e42f5b184d" />


## RESULT

Thus, histogram equalization was successfully implemented using OpenCV in Python. The original grayscale image was enhanced by redistributing its pixel intensity values. The original and equalized images and their histograms were displayed and compared to observe the improvement in image contrast.

