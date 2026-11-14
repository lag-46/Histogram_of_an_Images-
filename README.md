# Experiment 03 -- Histogram of Images

### Name : PANDEESWARAN N
### Reg No: 212224230191

## Aim

To perform histogram equalization on grayscale and color images using
OpenCV and visualize the original and equalized images along with their
histograms.

## Procedure

1.  Import the required Python libraries: OpenCV (`cv2`), NumPy, and
    Matplotlib.
2.  Read the input image `MyI.jpeg` in grayscale mode using
    `cv2.imread()`.
3.  Display the original grayscale image and plot its histogram.
4.  Apply histogram equalization to the grayscale image using
    `cv2.equalizeHist()`.
5.  Display the equalized grayscale image and its histogram.
6.  Read the input image again in color mode.
7.  Convert the color image from BGR to HSV color space using
    `cv2.cvtColor()`.
8.  Apply histogram equalization to the Value (V) channel of the HSV
    image.
9.  Convert the equalized HSV image back to BGR color space.
10. Display the equalized color image, compare it with the original
    image, and plot their histograms.

## Program

``` python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Histogram Equalization for Grayscale Images
img = cv2.imread('MyI.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

# Histogram Equalization for Color Images
img = cv2.imread('MyI.jpeg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

plt.figure(figsize=(20, 10))
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()

plt.figure(figsize=[15, 4])
plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()
```

## Output

 **Original Grayscale Image:** 
 
<img width="438" height="515" alt="image" src="https://github.com/user-attachments/assets/e3b7feb3-01e0-4766-8f30-6738baa63123" />


**Original Grayscale Histogram:** 

<img width="807" height="547" alt="image" src="https://github.com/user-attachments/assets/57e23f15-36d6-4d7b-b3aa-4531e9f03e58" />

**Equalized Grayscale Histogram:**

<img width="790" height="547" alt="image" src="https://github.com/user-attachments/assets/11af7afe-c6bf-4ae2-9ed1-3907325b4510" />

  
**Equalized Grayscale Image:** 

<img width="438" height="507" alt="image" src="https://github.com/user-attachments/assets/12e29f16-09ef-42b3-a600-d9998e91ffb5" />


**Equalized Color Image:**

<img width="372" height="312" alt="image" src="https://github.com/user-attachments/assets/40de14f1-9e0f-4979-8dd9-452e95f6a064" />


**Color Image Comparison:**

<img width="1093" height="317" alt="image" src="https://github.com/user-attachments/assets/69252441-b88c-4b64-8e91-a0eb09c5e788" />


**Histogram Comparison:** T

<img width="1092" height="310" alt="image" src="https://github.com/user-attachments/assets/8b43c7e7-a33f-4378-af58-04b6e976eeae" />


## Result

Thus, histogram equalization was successfully performed on grayscale and
color images using OpenCV. The original and equalized images and their
histograms were displayed and compared.
