# Exp-5--Record-Implementation-of-Filters
# Implementation-of-filter

## Aim

To implement filters for smoothing and sharpening images in the spatial domain.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import the required libraries.

### Step 2
Read the image and convert it from BGR to RGB.

### Step 3
Apply the required smoothing and sharpening filters to the image separately.

### Step 4
Plot and display the original and filtered images using `matplotlib.pyplot`.

### Step 5
End the program.

## Program

**Developed By:** DAKSHA C
**Register Number:** 212224230048

## 1. Smoothing Filters

### i) Using Averaging Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("my_photo.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```

### ii) Using Weighted Averaging Filter

```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show())
```

### iii) Using Gaussian Filter

```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

### iv) Using Median Filter

```python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

## 2. Sharpening Filters

### i) Using Laplacian Linear Kernel

```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

### ii) Using Laplacian Operator

```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## Output

### 1. Smoothing Filters

#### i) Using Averaging Filter

<img width="812" height="682" alt="Screenshot 2026-11-14 212811" src="https://github.com/user-attachments/assets/423a045f-d620-4408-b111-f4fa5b29f093" />


#### ii) Using Weighted Averaging Filter

<img width="597" height="460" alt="Screenshot 2026-11-14 212818" src="https://github.com/user-attachments/assets/54d6f81e-0cd5-4ffa-bf6e-bd28b85ef796" />


#### iii) Using Gaussian Filter

<img width="596" height="468" alt="Screenshot 2026-11-14 212823" src="https://github.com/user-attachments/assets/6cdf0c09-2567-4d1f-aba8-294eed90bcf1" />


#### iv) Using Median Filter

<img width="850" height="697" alt="Screenshot 2026-11-14 212830" src="https://github.com/user-attachments/assets/7e3ad204-6150-4357-9c3d-c6b05ef86b34" />


### 2. Sharpening Filters

#### i) Using Laplacian Kernel

<img width="596" height="457" alt="Screenshot 2026-11-14 212836" src="https://github.com/user-attachments/assets/b03ab5f8-4d2d-48e3-969b-a4c606e28d8a" />


#### ii) Using Laplacian Operator

<img width="580" height="467" alt="Screenshot 2026-11-14 212839" src="https://github.com/user-attachments/assets/2be55c1e-e1f2-4d4a-9d54-7ff52f5763f2" />


## Result

Thus, filters were implemented for smoothing and sharpening images in the spatial domain using OpenCV and Python.
