# EXPERIMENT 03 – HISTOGRAM EQUALIZATION USING OPENCV

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

## PROGRAM DEVELOPED BY

**Name:** FRANKLIN .F

**Register No.:** 212224240041

## PROGRAM

### Step 1: Import Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 2: Read the Input Image

```python
img = cv2.imread('WhatsApp Image 2026-10-24 at 3.32.56 PM.jpeg')

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

plt.figure(figsize=(8,6))
plt.imshow(gray, cmap='gray')
plt.title("Original Grayscale Image")
plt.axis('off')
plt.show()
```

### Step 3: Display the Histogram of Original Image

```python
hist = cv2.calcHist([gray], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.plot(hist)
plt.title("Histogram of Original Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Number of Pixels")
plt.show()
```

### Step 4: Apply Histogram Equalization

```python
equalized = cv2.equalizeHist(gray)

plt.figure(figsize=(8,6))
plt.imshow(equalized, cmap='gray')
plt.title("Histogram Equalized Image")
plt.axis('off')
plt.show()
```

### Step 5: Display Histogram of Equalized Image

```python
hist_equalized = cv2.calcHist([equalized], [0], None, [256], [0,256])

plt.figure(figsize=(8,5))
plt.plot(hist_equalized)
plt.title("Histogram of Equalized Image")
plt.xlabel("Pixel Intensity")
plt.ylabel("Number of Pixels")
plt.show()
```

### Step 6: Compare Original and Equalized Images

```python
plt.figure(figsize=(12,6))

plt.subplot(1,2,1)
plt.imshow(gray, cmap='gray')
plt.title("Original Image")
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(equalized, cmap='gray')
plt.title("Equalized Image")
plt.axis('off')

plt.show()
```

### Step 7: Compare Both Histograms

```python
plt.figure(figsize=(12,5))

plt.subplot(1,2,1)
plt.plot(hist)
plt.title("Original Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")

plt.subplot(1,2,2)
plt.plot(hist_equalized)
plt.title("Equalized Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")

plt.show()
```

## OUTPUT

<img width="523" height="535" alt="image" src="https://github.com/user-attachments/assets/c8e77dd3-f610-4b61-b074-1ddb2e5ddcb9" />
<img width="835" height="538" alt="image" src="https://github.com/user-attachments/assets/38c867ec-058b-47b4-a737-4c3e1b46cdb6" />
<img width="752" height="537" alt="image" src="https://github.com/user-attachments/assets/8cb24847-6b40-4dfd-9f96-bb2518fb7363" />
<img width="480" height="532" alt="image" src="https://github.com/user-attachments/assets/d26897cb-f63b-444c-95b7-7bcb78e08ca7" />
<img width="517" height="550" alt="image" src="https://github.com/user-attachments/assets/7ef40b5e-038a-4a74-8eea-e4b9f1451bbe" />
<img width="727" height="532" alt="image" src="https://github.com/user-attachments/assets/2abd1a74-a47b-47ed-8b88-da19570c56ed" />
<img width="1442" height="523" alt="image" src="https://github.com/user-attachments/assets/2ec4aa42-2d09-4a0f-a815-9aa3b6d0d424" />
<img width="1390" height="427" alt="image" src="https://github.com/user-attachments/assets/7a18f9b7-4353-468a-8ee3-fe93d388bded" />


## RESULT

Thus, histogram equalization was successfully implemented using OpenCV in Python. The original grayscale image was enhanced by redistributing its pixel intensity values. The original and equalized images and their histograms were displayed and compared to observe the improvement in image contrast.

