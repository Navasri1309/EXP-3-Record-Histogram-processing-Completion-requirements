# EXP-3-Record-Histogram-processing-Completion-requirements

### Developed By: NAVASRI B

### Register Number: 212225230196

# Histogram-of-an-images

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

```
python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('image.jpeg', cv2.IMREAD_GRAYSCALE)

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

img = cv2.imread('image.jpeg', cv2.IMREAD_COLOR)
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

## Output

### Input Grayscale Image

<img width="382" height="450" alt="image" src="https://github.com/user-attachments/assets/1752b963-9d2d-4acc-8e99-329ac04ddb45" />

### Input Grayscale Image Range

<img width="601" height="443" alt="image" src="https://github.com/user-attachments/assets/c5363ade-852c-4d4f-9130-3122b7b32a9e" />


### Input Grayscale Image Equalized Histogram

<img width="627" height="442" alt="image" src="https://github.com/user-attachments/assets/7142aaf6-c106-4486-87cf-fc655e049344" />

### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="395" height="450" alt="image" src="https://github.com/user-attachments/assets/e3b09bda-a5e7-4c73-9806-8a265b75a255" />

### Equalized Image

<img width="382" height="453" alt="image" src="https://github.com/user-attachments/assets/8db4c0c4-dfe8-4901-b964-705c536de7d7" />


### Equalized Histogram

<img width="631" height="456" alt="image" src="https://github.com/user-attachments/assets/d9047547-302a-429a-baeb-19e2a7c68b42" />


### Final Output of Original Image and Equalized 

<img width="862" height="317" alt="image" src="https://github.com/user-attachments/assets/2778f69f-ac92-49ec-a268-b2e6085b3698" />


### Final Output of Original Image and its Histogram Equalized

<img width="873" height="272" alt="image" src="https://github.com/user-attachments/assets/3a0c99e0-2f8e-4a97-b40b-003ee233c136" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
