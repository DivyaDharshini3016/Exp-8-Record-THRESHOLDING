# Exp-8-Record-THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
Anaconda - Python 3.7
OpenCV

## Algorithm
### Step1:
Import all the necessary modules for the program.
### Step2:
Read the image and convert to grayscale

### Step3:
Use Global Thresholding to segment the image

### Step4:
Use Adaptive Thresholding to segment the image

### Step5:
Use Otsu's method to segment the image

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Read the image and convert to grayscale
image = cv2.imread('image.JPG')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```

## Output
### Original Image

<img width="751" height="306" alt="image" src="https://github.com/user-attachments/assets/c90b28c9-7dba-49e2-9997-31fc3f12f0ee" />

### Global Thresholding

<img width="526" height="300" alt="image" src="https://github.com/user-attachments/assets/7a7d4c1b-56d2-4742-93ba-aef4d73dbbb2" />

### Adaptive Thresholding

<img width="362" height="313" alt="image" src="https://github.com/user-attachments/assets/e9d9cb27-5c95-4db3-a854-dd2f9d96454f" />

### Optimum Global Thesholding using Otsu's Method

<img width="477" height="317" alt="image" src="https://github.com/user-attachments/assets/f00763e1-f0a6-4985-937a-c03d2bda795b" />

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
