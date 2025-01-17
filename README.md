## EX.NO: 09 <br>
## DATE: 26-05-2022
## <p align="center">THRESHOLDING</p>

## Aim:

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:

1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("porsche.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("porsche.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## OUTPUT:

### Original Image and Grayscale Image

![image](https://user-images.githubusercontent.com/74660507/169488404-f744eafb-5f36-40df-a86a-639ac6d11fef.png)

### Global Thresholding
![image](https://user-images.githubusercontent.com/74660507/169488559-3885518c-eee9-4081-85dd-80fab1c5b415.png)

![image](https://user-images.githubusercontent.com/74660507/169488714-5a7cc57a-0c3c-46d5-a104-b94f4f0d35b1.png)

![image](https://user-images.githubusercontent.com/74660507/169489007-6c3e25a5-60bb-43c5-a24a-601f3360ffd9.png)

![image](https://user-images.githubusercontent.com/74660507/169489142-ee47baf3-9068-48a3-b951-027022b8b7fd.png)

![image](https://user-images.githubusercontent.com/74660507/169489357-9d801fac-0d1b-4a2e-9552-124ae80ab28e.png)

### Adaptive Thresholding

![image](https://user-images.githubusercontent.com/74660507/169489509-bb25349c-9e10-4b43-89f6-07ae330ea2f3.png)

![image](https://user-images.githubusercontent.com/74660507/169489676-46afb2f6-eada-4502-8d3e-73425dd74903.png)

### Optimum Global Thesholding using Otsu's Method

![image](https://user-images.githubusercontent.com/74660507/169489816-9630e0f4-a80a-4445-b047-93da4e4f4847.png)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
