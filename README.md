# THRESHOLDING

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

## Program

```python
# Name: Naveen Jaisanker
# Reg No: 212224110039

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale

image = cv2.imread('chandelier.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('chandelier.jpg',0)

# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

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
## Output

### Original Image

![Screenshot 2025-04-23 222410](https://github.com/user-attachments/assets/7dee7653-ddca-4b22-97ed-0be7e9964176)

### Global Thresholding

![Screenshot 2025-04-23 222424](https://github.com/user-attachments/assets/a1c69e8b-fb9f-43dc-90df-15cf9079d03b)

![Screenshot 2025-04-23 222430](https://github.com/user-attachments/assets/6525d9b4-88ea-4b43-8bae-00539efc3b36)

![Screenshot 2025-04-23 222436](https://github.com/user-attachments/assets/4b564c44-0682-46e9-9e3c-3e4068542a86)

![Screenshot 2025-04-23 222442](https://github.com/user-attachments/assets/5be91c53-dd22-4db1-ad7a-216d929d8575)

![Screenshot 2025-04-23 222449](https://github.com/user-attachments/assets/05447eeb-a012-4333-9dbb-b2b0562129dc)

### Adaptive Thresholding

![Screenshot 2025-04-23 222454](https://github.com/user-attachments/assets/24ba156a-d37a-49c9-987c-fee1fcc6fe4a)

![Screenshot 2025-04-23 222500](https://github.com/user-attachments/assets/5f54a9a5-edc5-42d5-a9a1-4c2d07921de4)

### Optimum Global Thesholding using Otsu's Method

![Screenshot 2025-04-23 222505](https://github.com/user-attachments/assets/7e2e6a68-642c-4414-8481-d94514dd43d1)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
