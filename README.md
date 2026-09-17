# Ex.No:5 Implementation of filter
# Name: VIJAY K   
# Register No: 212224240182

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

##  Developed By

  
  ```
  import cv2
  import numpy as np
  import matplotlib.pyplot as plt
  ```
  ```
  img = cv2.imread("image 5.jpg")
  img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
  ```
  ```
  plt.imshow(img)
  plt.title("Original Image")
  plt.axis("off")
  plt.show()
  ```
  1. Averaging Filter
  ```
  avg = cv2.blur(img, (5,5))
  plt.imshow(avg)
  plt.title("Averaging Filter")
  plt.axis("off")
  plt.show()
  ```
  2. Weighted Averaging Filter
  ```
  kernel = np.array([[1,2,1],
                   [2,4,2],
                   [1,2,1]], np.float32) / 16
  weighted = cv2.filter2D(img, -1, kernel)
  plt.imshow(weighted)
  plt.title("Weighted Averaging Filter")
  plt.axis("off")
  plt.show()
  ```
3. Gaussian Filter
```
gaussian = cv2.GaussianBlur(img, (5,5), 0)
plt.imshow(gaussian)
plt.title("Gaussian Filter")
plt.axis("off")
plt.show()
```
4. Median Filter
```
median = cv2.medianBlur(img, 5)
plt.imshow(median)
plt.title("Median Filter")
plt.axis("off")
plt.show()
```
5. Laplacian Sharpening (Kernel)
```
kernel = np.array([[0,-1,0],
                   [-1,5,-1],
                   [0,-1,0]])
sharp = cv2.filter2D(img, -1, kernel)
plt.imshow(sharp)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
6. Laplacian Operator
```
lap = cv2.Laplacian(img, cv2.CV_64F)
lap = np.uint8(np.absolute(lap))
plt.imshow(lap)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

##  Output

### Smoothing Filters

- Original Image 
<img width="717" height="279" alt="download" src="https://github.com/user-attachments/assets/f0dbf27e-7dad-4d54-9ae5-e0a1d5e64c0c" />




- Weighted averaging provides smoother result with less distortion

<img width="717" height="279" alt="download" src="https://github.com/user-attachments/assets/283e145d-0253-47c0-979d-793290f691c3" />



 
- Gaussian filter preserves edges better while reducing noise


<img width="516" height="210" alt="download" src="https://github.com/user-attachments/assets/d9205f14-1a37-4547-827c-9e9d56da40ae" />


- Median filter removes salt-and-pepper noise effectively


<img width="717" height="279" alt="download" src="https://github.com/user-attachments/assets/2fd7742e-4f4b-47a8-a2b5-cec0595f6773" />



###  Sharpening Filters

<img width="516" height="210" alt="download" src="https://github.com/user-attachments/assets/12028bde-cab7-4a56-ade2-bbaefd4a337e" />

<img width="516" height="210" alt="download" src="https://github.com/user-attachments/assets/00e5ff88-0a9b-499d-ab00-ffa4cc52506b" />





---

##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
