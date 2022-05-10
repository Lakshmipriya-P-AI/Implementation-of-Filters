# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

### Step2
Convert the saved BGR image to RGB using cvtColor().

### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.

### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().

## Program:
```
Developed By   : Lakshmi priya.P
Register Number: 212221230053
```
### 1. Smoothing Filters
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("image.jfif")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
```

i) Using Averaging Filter
```
kernel1 = np.ones((11,11),np.float32)/121
avg_filter = cv2.filter2D(original_image,-1,kernel1)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(avg_filter)
plt.title("Filtered")
plt.axis("off")
```
ii) Using Weighted Averaging Filter
```
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")
```

iii) Using Gaussian Filter
```
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")
```

iv) Using Median Filter
```
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")
```

### 2. Sharpening Filters

i) Using Laplacian Kernal
```
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off")
```

ii) Using Laplacian Operator
```
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")
```

## OUTPUT:
### 1. Smoothing Filters

i) Using Averaging Filter

![ex6 1](https://user-images.githubusercontent.com/93427923/167538440-7b3f9cbc-d974-4e40-bec2-b34b901f3b55.png)

ii) Using Weighted Averaging Filter

![ex6 2](https://user-images.githubusercontent.com/93427923/167538470-6474ef83-3e68-423e-bac4-6dc2231e121b.png)

iii) Using Gaussian Filter

![ex6 3](https://user-images.githubusercontent.com/93427923/167538612-b9ecaa0e-64b6-484e-b062-fc54df695c90.png)

iv) Using Median Filter

![ex6 4](https://user-images.githubusercontent.com/93427923/167538668-c9645572-d526-46cb-9fbb-7b7c3b660cc1.png)

### 2. Sharpening Filters

i) Using Laplacian Kernal

![ex6 5](https://user-images.githubusercontent.com/93427923/167538750-368099e0-e7f3-4840-8ac1-cd8f20ae2327.png)

ii) Using Laplacian Operator

![ex6 6](https://user-images.githubusercontent.com/93427923/167538800-3172c2b3-9b94-4fda-94a2-b1d261101878.png)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
