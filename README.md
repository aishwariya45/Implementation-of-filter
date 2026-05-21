# Implementation-of-filter

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1

Import the required libraries.
Step2

Convert the image from BGR to RGB.

Step3

Apply the required filters for the image separately.
Step4

Plot the original and filtered image by using matplotlib.pyplot.
Step5

End the program.


# PROGRAM 
### NAME : S.AISHWARIYA
### REG NO : 212224240005
## 1. SMOOTHING FILTERS
i)Using Averaging Filter
```

import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("rose.jpg")
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
<img width="859" height="315" alt="image" src="https://github.com/user-attachments/assets/907dd957-46a0-4e13-b639-99266dd248c8" />

ii) Using Weighted Averaging Filter

```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()


```
<img width="938" height="320" alt="image" src="https://github.com/user-attachments/assets/4cbdaeee-94d1-40c7-aad0-d2d05dfebe68" />


iii) Using Gaussian Filter

```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```
<img width="680" height="235" alt="image" src="https://github.com/user-attachments/assets/43578b46-944c-4683-a2b4-7561f53d109b" />

iv)Using Median Filter
```
median=cv2.medianBlur(image2,13)
plt.title("Median Blur")
plt.axis('off')
plt.show()


```
<img width="1041" height="342" alt="image" src="https://github.com/user-attachments/assets/37972fe7-101c-41d5-a441-b5d254be79e5" />

## 2. Sharpening Filters
i) Using Laplacian Linear Kernal

```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()


```
<img width="733" height="253" alt="image" src="https://github.com/user-attachments/assets/c8541040-b36d-4274-b144-c34035a295b3" />

ii) Using Laplacian Operator

```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()


```

<img width="684" height="266" alt="image" src="https://github.com/user-attachments/assets/ed0379ad-a4b0-4a69-a489-0ef08daa88a3" />

# RESULT:

Thus the filters are designed for smoothing and sharpening the images in the spatial domain.


