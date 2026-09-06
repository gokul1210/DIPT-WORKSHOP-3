# DIPT-WORKSHOP-3
# Canny Edge Detection using OpenCV
## Author
## NAME : GOKUL S
## REG.NO : 212224230075
## Overview

This project demonstrates the implementation of the Canny Edge Detection algorithm using Python and OpenCV. Canny Edge Detection is a widely used image processing technique for identifying object boundaries and significant intensity changes in an image.

## Objectives

- Load and process a sample image.
- Convert the image to grayscale.
- Apply the Canny Edge Detection algorithm.
- Visualize and analyze the detected edges.
- Study the impact of different threshold parameters on edge detection results.

## Technologies Used

- Python
- OpenCV
- NumPy
- Matplotlib
- Jupyter Notebook


## Algorithm

1. Read the input image.
2. Convert the image to grayscale.
3. Apply Gaussian filtering to reduce noise.
4. Compute image gradients.
5. Perform non-maximum suppression.
6. Apply double thresholding.
7. Track edges using hysteresis.
8. Display the detected edges.


## Applications

- Object Detection
- Image Segmentation
- Medical Image Analysis
- Autonomous Vehicles
- Computer Vision Systems
- Pattern Recognition

## Requirements

```bash
pip install opencv-python numpy matplotlib
```

## Running the Project

1. Clone the repository:

```bash
git clone https://github.com/your-username/canny-edge-detection-opencv.git
```

2. Open Jupyter Notebook:

```bash
jupyter notebook
```

3. Run:

```bash
CANNY EDGE DETECTION.ipynb
```
## PROGRAM 
```
import cv2
import matplotlib.pyplot as plt
import os

path = "lion.png"

# 1. Verify existence
if not os.path.exists(path):
    raise FileNotFoundError(f"Cannot find image at: {os.path.abspath(path)}")

image = cv2.imread(path)

# 2. Display with OpenCV's BGR to RGB conversion
# OpenCV reads in BGR, while Matplotlib expects RGB:
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.title("Original Image - LION")
plt.axis('off')
plt.imshow(image_rgb)
plt.show()
```

<img width="773" height="394" alt="image" src="https://github.com/user-attachments/assets/53921b35-ed7f-443c-aa8e-6cb23b1a6f10" />


```
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Case 1: Low Thresholds
blur1 = cv2.GaussianBlur(gray, (5, 5), 0.1)
canny1 = cv2.Canny(blur1, 50, 100)

plt.subplot(2, 2, 1)
plt.imshow(canny1, cmap='gray')
plt.title('Low Thresholds (50,100)')
plt.axis('off')

# Case 2: Medium Thresholds
blur2 = cv2.GaussianBlur(gray, (5, 5), 0.1)
canny2 = cv2.Canny(blur2, 100, 200)

plt.subplot(2, 2, 2)
plt.imshow(canny2, cmap='gray')
plt.title('Medium Thresholds (100,200)')
plt.axis('off')

# Case 3: High Thresholds
blur3 = cv2.GaussianBlur(gray, (5, 5), 0.1)
canny3 = cv2.Canny(blur3, 200, 300)

plt.subplot(2, 2, 3)
plt.imshow(canny3, cmap='gray')
plt.title('High Thresholds (200,300)')
plt.axis('off')

# Case 4: Strong Gaussian Blur
blur4 = cv2.GaussianBlur(gray, (9, 9), 2)
canny4 = cv2.Canny(blur4, 100, 200)

plt.subplot(2, 2, 4)
plt.imshow(canny4, cmap='gray')
plt.title('Strong Blur (9x9, sigma=2)')
plt.axis('off')

plt.tight_layout()
plt.show()
```

<img width="976" height="544" alt="image" src="https://github.com/user-attachments/assets/097c5daf-fc5d-40b9-8653-677c5949d35e" />


## Conclusion

The Canny Edge Detection algorithm effectively detects object boundaries and important image features. The quality of edge detection depends on the selected threshold values, making parameter tuning an essential part of image processing applications.



## License

This project is licensed under the MIT License.
