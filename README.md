## Image-Handling-and-Pixel-Transformations-Using-OpenCV
## AIM:
Write a Python program using OpenCV that performs the following tasks:

1.Read and Display an Image.
2.Adjust the brightness of an image.
3.Modify the image contrast.
4.Generate a third image using bitwise operations.
## Software Required:
• Anaconda - Python 3.7
• Jupyter Notebook (for interactive development and execution)
## Algorithm:
## Step 1:
Load an image from your local directory and display it.

## Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

## Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.
Display the original, brighter, and darker images.

## Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).
Display the original, lower contrast, and higher contrast images.

## Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

Program Developed By:
Name:  Kruthika R
Register Number: 212225240075
## Ex. No. 01 – Digital Image Processing Using OpenCV
## 1. Import Libraries
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
## 2. Read and Display an Image
```
# Read image
img = cv2.imread('exp1 img.jpg')

# Convert BGR to RGB
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Display image
plt.imshow(img)
plt.title('Original Image')
plt.axis('off')
plt.show()
```
## 3. Adjust Brightness
```
# Create a matrix of ones
M = np.ones(img.shape, dtype='float64')

# Increase brightness
bright = cv2.add(img, M * 50)

# Decrease brightness
dark = cv2.subtract(img, M * 50)

# Display images
plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(img)
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(bright)
plt.title('Brighter Image')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(dark)
plt.title('Darker Image')
plt.axis('off')

plt.show()
```
## 4. Modify Image Contrast
```
# Lower contrast
low_contrast = cv2.convertScaleAbs(img, alpha=0.8, beta=0)

# Higher contrast
high_contrast1 = cv2.convertScaleAbs(img, alpha=1.1, beta=0)
high_contrast2 = cv2.convertScaleAbs(img, alpha=1.2, beta=0)

# Display images
plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(img)
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(low_contrast)
plt.title('Low Contrast')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(high_contrast2)
plt.title('High Contrast')
plt.axis('off')

plt.show()
```

## 5. Split Image into B, G, R Components
```
# Read image in BGR format
img = cv2.imread('boy.jpg')

# Split image into channels
B, G, R = cv2.split(img)

# Display individual channels
plt.figure(figsize=(12, 5))

plt.subplot(1, 3, 1)
plt.imshow(B, cmap='gray')
plt.title('Blue Channel')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(G, cmap='gray')
plt.title('Green Channel')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(R, cmap='gray')
plt.title('Red Channel')
plt.axis('off')

plt.show()
```
## 6. Generate Third Image Using Bitwise Operations
```
img = cv2.imread('fox.jpg')
# Create a mask
mask = np.zeros(img.shape[:2], dtype=np.uint8)

# Draw a white rectangle on mask
cv2.rectangle(mask, (50, 50), (300, 300), 255, -1)

# Apply bitwise AND operation
result = cv2.bitwise_and(img, img, mask=mask)

# Display images
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(result, cv2.COLOR_BGR2RGB))
plt.title('Bitwise AND Result')
plt.axis('off')

plt.show()
```
Output:
## Original image
<img width="637" height="507" alt="image" src="https://github.com/user-attachments/assets/efd30dd7-578c-4048-a63d-92f1ab1c47ee" />

## Adjust Brightness
<img width="1237" height="345" alt="image" src="https://github.com/user-attachments/assets/8c12dc33-3806-41d8-9d6e-0307dbccb9a8" />

## Contrast image
<img width="1207" height="320" alt="image" src="https://github.com/user-attachments/assets/4f01a02f-0bb6-4d89-8691-7e65c4f44601" />

## Image of B, G, R Components
<img width="1185" height="328" alt="image" src="https://github.com/user-attachments/assets/f327cdbd-eefc-4be1-b921-c6bf1782f8c8" />

## Third Image Using Bitwise Operations
<img width="1192" height="473" alt="image" src="https://github.com/user-attachments/assets/3114e94a-b60c-4ee2-b5d5-1fb3c7ca903f" />
