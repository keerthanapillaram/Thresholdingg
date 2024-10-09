## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program :
```
Developed By : P Keerthana
Register Number : 212223240069
```

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

# Read the Image and convert to grayscale
```python

image = cv2.imread('fish.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
# Display the original grayscale image
```python

plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
#### gray Image
![Screenshot 2024-10-09 160350](https://github.com/user-attachments/assets/91bce35b-b350-4d05-99fd-eee88d96968a)
<br>
# Use Global thresholding to segment the image
```python

ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Global Thresholding
![Screenshot 2024-10-09 160358](https://github.com/user-attachments/assets/87f0a485-3de4-481b-b485-a11cd454e304)
<br>
# Use Adaptive thresholding to segment the image
```python
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
### Adaptive Thresholding
![Screenshot 2024-10-09 160408](https://github.com/user-attachments/assets/41145713-fa0f-4831-ac64-b12e55f47689)
<br>
# Use Otsu's method to segment the image
```python
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()
```
### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-10-09 160415](https://github.com/user-attachments/assets/5fb0ddf7-19f5-4da2-8b04-5e28d29293db)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
