# Histogram-of-an-images

# **Name:** GOKUL S

# **Register Number:** 212224240045


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

**Developed By:** GOKUL S

**Register Number:** 212224240045

python

### Step1 : Histogram Equalization for Grayscale Images

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('ig.png', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
```

```python
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Step2 : Histogram Equalization for Color Images

```python
img = cv2.imread('ig.png', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
```python
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
```python
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```




## Output

### Input Grayscale Image

<img width="348" height="434" alt="download" src="https://github.com/user-attachments/assets/e0e12d4e-ed77-468f-a869-2b779456a153" />


### Input Grayscale Image Range

<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/f1db2d97-69ee-4fa7-8a03-d35425f39e97" />


### Input Grayscale Image Equalized Histogram

<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/6d03fe1e-8cc0-42b6-80c8-fcb7dea3544c" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="348" height="434" alt="download" src="https://github.com/user-attachments/assets/3df12843-ec79-4397-99cb-3715a7af52e9" />


### Equalized Image

<img width="348" height="434" alt="download" src="https://github.com/user-attachments/assets/8584ec79-7a96-4d99-9beb-ed84089b0177" />


### Equalized Histogram

<img width="579" height="434" alt="download" src="https://github.com/user-attachments/assets/bb831bb7-f6d3-40a2-a1fe-87b393310cf0" />


### Final Output of Original Image and Equalized 

<img width="1178" height="414" alt="download" src="https://github.com/user-attachments/assets/c4d926bc-8c3e-4fca-8e07-38ec863ba5e0" />


### Final Output of Original Image and its Histogram Equalized

<img width="1246" height="372" alt="download" src="https://github.com/user-attachments/assets/cd95f9f3-5eca-485b-a350-4f2a5292e18f" />


## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
