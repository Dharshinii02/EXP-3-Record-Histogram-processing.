# EXP-3-Record-Histogram-Processing

### Developed By:

**Name:** Dharshini J

**Register Number:** 212224240036

---

## Aim

To write a Python program using OpenCV to perform histogram processing on grayscale and color images by displaying histograms and applying histogram equalization to improve image contrast.

---

##  Software Used

- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

---

##  Algorithm

### Step 1: Import Required Libraries

Import OpenCV, NumPy, and Matplotlib libraries for image processing and visualization.

### Step 2: Read and Display a Grayscale Image

1. Read the input image using `cv2.imread()` in grayscale mode.
2. Display the grayscale image using Matplotlib.
3. Set the colormap to gray.

### Step 3: Display the Original Histogram

1. Convert the image into a one-dimensional array using `img.ravel()`.
2. Calculate the histogram using `plt.hist()`.
3. Display the histogram with 256 intensity levels.

### Step 4: Perform Histogram Equalization on Grayscale Image

1. Apply histogram equalization using `cv2.equalizeHist()`.
2. Display the equalized histogram.
3. Display the histogram-equalized grayscale image.

### Step 5: Perform Histogram Equalization on Color Image

1. Read the original image in color mode.
2. Convert the BGR image into HSV color space using `cv2.cvtColor()`.
3. Apply histogram equalization to the Value (V) channel.
4. Convert the HSV image back to BGR.
5. Display the equalized color image.

### Step 6: Display the Equalized Histogram

1. Calculate the histogram of the equalized color image.
2. Display the histogram using Matplotlib.

### Step 7: Compare Original and Equalized Images

1. Display the original color image.
2. Display the histogram-equalized color image.
3. Display the original histogram.
4. Display the equalized histogram.
5. Compare the results using Matplotlib subplots.

### Step 8: Display Histograms Side by Side

1. Create a figure using `plt.figure()`.
2. Display the original image histogram.
3. Display the histogram-equalized image histogram.
4. Compare both histograms side by side.

---

##  Program





### 1. Import Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### 2. Read and Display the Grayscale Image

```python
img = cv2.imread('image.jpeg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('GRAYSCALE Image')
plt.show()
```

### 3. Display the Original Histogram

```python
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('GRAYSCALE Image')
plt.show()
```

### 4. Perform Histogram Equalization on Grayscale Image

```python
img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### 5. Perform Histogram Equalization on Color Image

```python
img = cv2.imread('image.jpeg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.show()
```

### 6. Display the Equalized Histogram

```python
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()
```

### 7. Compare Original and Equalized Images

```python
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')

plt.show()
```

### 8. Display Histograms Side by Side

```python
plt.figure(figsize=[15, 4])

plt.subplot(121)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')

plt.subplot(122)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')

plt.show()
```

---

## Output

The following outputs are obtained:

### i) Display the Grayscale Image

<img width="422" height="432" alt="image" src="https://github.com/user-attachments/assets/8755d8e3-e34e-4760-998e-486c50c93dad" />


### ii) Display the Original Histogram

<img width="632" height="437" alt="image" src="https://github.com/user-attachments/assets/e6ae8064-8c7d-45ba-bb4e-25e9f94d7efd" />


### iii) Display the Equalized Histogram

<img width="628" height="437" alt="image" src="https://github.com/user-attachments/assets/a1b44ffb-d3a8-4fcb-8681-071ad7365503" />


### iv) Display the Histogram Equalized Grayscale Image

<img width="437" height="446" alt="image" src="https://github.com/user-attachments/assets/4bab195e-1054-45d8-ac62-3d6b4311f0ae" />

### v) Display the Equalized Color Image

<img width="437" height="452" alt="image" src="https://github.com/user-attachments/assets/087f7f10-a715-4e80-8576-a8f595d50e81" />

### vi) Display the Histogram Equalized Image Histogram

<img width="631" height="437" alt="image" src="https://github.com/user-attachments/assets/55d96fc8-b03f-4c22-b667-458d5baf08fe" />


### vii) Compare Original and Equalized Images with Histograms

<img width="622" height="450" alt="image" src="https://github.com/user-attachments/assets/6e48cb1f-6fd5-4ed9-a44d-fd1b9b067103" />


### viii) Display Original and Equalized Histograms Side by Side

<img width="1117" height="336" alt="image" src="https://github.com/user-attachments/assets/caac1ff8-a1a6-4428-a54c-3933e2e34bd2" />

---

## Result

Thus, histogram processing was successfully performed using Python and OpenCV. Histogram equalization was applied to both grayscale and color images, and the original and equalized images and their histograms were displayed and compared using Matplotlib.
