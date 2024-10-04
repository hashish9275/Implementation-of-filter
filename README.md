# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1: 
Import necessary libraries (cv2, NumPy, Matplotlib) for image loading, filtering, and visualization.

### Step 2: 
Load the image using cv2.imread() and convert it to RGB format using cv2.cvtColor() for proper display in Matplotlib.

### Step 3: 
Apply different filters:
1. Averaging Filter: Define an averaging kernel using np.ones() and apply it to the image using cv2.filter2D().
2. Weighted Averaging Filter: Define a weighted kernel (e.g., 3x3 Gaussian-like) and apply it with cv2.filter2D().
3. Gaussian Filter: Use cv2.GaussianBlur() to apply Gaussian blur.
4. Median Filter: Use cv2.medianBlur() to reduce noise.
5. Laplacian Operator: Use cv2.Laplacian() to apply edge detection.
    

### Step 4: 
Display each filtered image using plt.subplot() and plt.imshow() for side-by-side comparison of the original and processed images.

### Step 5: 
Save or show the images using plt.show() after applying each filter to visualize the effects of smoothing and sharpening.

```
Program:
Developed By   : K.R.Hashish Vidya Sagar
Register Number: 212222230047
```
*
```
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread("car.jpg")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

plt.figure(figsize=(7, 3))
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
```
## Output:
![image](https://github.com/user-attachments/assets/ba94c0ad-7c16-4a79-a456-397e6ccec339)


### 1. Smoothing Filters

## i) Using Averaging Filter
```
kernel = np.ones((11, 11), np.float32) / 121
averaging_image = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(7, 3))
plt.imshow(averaging_image)
plt.title("Averaging Filter Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/74f2cd10-8b3e-45d6-9bed-729c7eadf530)

## ii) Using Weighted Averaging Filter
```
kernel1 = np.array([[1, 2, 1],
                    [2, 4, 2],
                    [1, 2, 1]]) / 16

weighted_average_image = cv2.filter2D(image2, -1, kernel1)
plt.figure(figsize=(7, 3))
plt.imshow(weighted_average_image)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/27ed4897-f13a-4654-a9f6-d7f884d96e0b)


## iii) Using Gaussian Filter
```
gaussian_blur = cv2.GaussianBlur(image2, (11, 11), 0)

plt.figure(figsize=(7, 3))
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/03630bc2-1304-419e-8593-221a4ba07e7c)

## iv)Using Median Filter
```
median_blur = cv2.medianBlur(image2, 11)
plt.figure(figsize=(7, 3))
plt.imshow(median_blur)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
![image](https://github.com/user-attachments/assets/e6a63908-1b2d-4957-aa56-881fbd468597)

## 2. Sharpening Filters
## i) Using Laplacian Linear Kernal
```
sharpened_image = cv2.filter2D(image2, -1, kernel1)

plt.figure(figsize=(7, 3))
plt.imshow(sharpened_image)
plt.title("Sharpened Image (Laplacian Kernel)")
plt.axis("off")
plt.show()
```

## ii) Using Laplacian Operator
```
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.figure(figsize=(7, 3))
plt.imshow(laplacian, cmap='gray')
plt.title("Laplacian Operator Image")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/268f1b34-b699-4649-8325-0e939f5abd6d)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
