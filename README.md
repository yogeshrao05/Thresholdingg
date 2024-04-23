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
```
DEVELOPED BY: Yogesh rao S D
REGISTER NO: 212222110055
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("disney.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("disney.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/c087fd60-87cf-44e6-b441-d15cd0dfc9b9)

### Global Thresholding
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/1034f7d5-8145-4bde-8edb-3689bedb9b3a)
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/3983b06c-24f6-4aa0-b156-cd1a2fdfa773)
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/8bd853d0-1bde-4e1c-8662-8075424a9b83)
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/dea8a1a7-c193-46d2-aaaa-1d253ffbfb01)
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/6e88fd21-db5b-45e8-a9b2-a4fb089ee182)

### Adaptive Thresholding
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/33b9138d-60e0-47cc-baaf-76114a4b1e2b)
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/7f3f4979-9c36-42fb-8f34-9e92d13302fd)

### Optimum Global Thesholding using Otsu's Method
![download](https://github.com/srikarthickeyanganapathy/THRESHOLDING-/assets/119393842/c04d0d6c-b15c-4025-978b-47471858002d)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
