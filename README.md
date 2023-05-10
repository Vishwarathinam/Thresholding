### Thresholding of Images
### Aim:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

### Software Required
1. Anaconda - Python 3.7
2. OpenCV

### Algorithm

### Step1:
Load the necessary packages requiured for the processing the threshold of the image.

### Step2:
Read the Image using the cv2 instructions and convert it to a grayscale image.

### Step3:
Apply global thresholding on the grayscale image and store the results in threshold variables. Use different thresholding methods to segment the image.

### Step4:
Apply adaptive thresholding on the grayscale image and store the results in the variables th1 and th2. Use different adaptive thresholding methods to segment the immage.

### Step5:
Apply Otsu's method on the grayscale image and store the result in variable th3.

### Step 6:
Create a list titles containing the titles of each image and a list images containing the corresponding images.

### Step 7:
Loop through the images list to display each image alongside its title using plt.subplot(), plt.title(), plt.imshow(), plt.axis(), and plt.show().

### Step 8:
End the program.
## Program
```
Developed By: Vishwa Rathinam. S
Register Number: 212221240063
Program to segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.
```
```
# Load the necessary packages:

import cv2
import matplotlib.pyplot as plt
import numpy as np
```

```
# Read the Image and convert to grayscale:

image=cv2.imread("car.jpg")
image1=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
```

```
# Use Global thresholding to segment the image:

ret, thresh1 = cv2.threshold(image1,100,220,cv2.THRESH_BINARY)
ret, thresh2 = cv2.threshold(image1,90,160, cv2.THRESH_BINARY_INV)
ret, thresh3 = cv2.threshold(image1,140,220,cv2.THRESH_TRUNC)
ret, thresh4 = cv2.threshold(image1,100,200,cv2.THRESH_TOZERO)
ret, thresh5 = cv2.threshold(image1,225,270,cv2.THRESH_TOZERO_INV)

```

```
# Use Adaptive thresholding to segment the image:

th1 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_MEAN_C, cv2.THRESH_BINARY, 11, 3)
th2 = cv2.adaptiveThreshold(image1, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 3)

```
```
# Use Otsu's method to segment the image:

ret2, th3 = cv2.threshold(image1, 150, 255, cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```

```
# Display the results:

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (Truncate)",
       "Threshold Image (To Zero)","Threshold Image (To Zero-Inverse)","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)","Otsu"]
images=[image1,thresh1,thresh2,thresh3,thresh4,thresh5,th1,th2,th3]
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
### Output:

### Original Image
![c1](https://github.com/Vishwarathinam/Thresholding/assets/95266350/4322f15a-f116-476d-8274-229954027053)


### Global Thresholding
![c2](https://github.com/Vishwarathinam/Thresholding/assets/95266350/86166e0a-3a55-4804-82e8-98b13e0f1eee)
![c3](https://github.com/Vishwarathinam/Thresholding/assets/95266350/cc38353a-cc48-449d-959f-8cb8cbac1da3)
![c4](https://github.com/Vishwarathinam/Thresholding/assets/95266350/6f64bd7f-bc94-4181-a22e-b9ec4b07bf3b)


### Adaptive Thresholding
![c5](https://github.com/Vishwarathinam/Thresholding/assets/95266350/be7c9e41-0248-4229-b4d9-af6e7d06cd5a)


### Optimum Global Thesholding using Otsu's Method
![c6](https://github.com/Vishwarathinam/Thresholding/assets/95266350/2c54c96e-33d6-4fd1-a6b3-81bafc0282e4)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

