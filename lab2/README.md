# ImageMaster: Image Processing and Compression

## Description

**ImageMaster** is a Python-based graphical user interface (GUI) application that allows users to perform various image processing tasks. The project implements element-wise operations, linear contrast adjustments, and global thresholding methods for image compression and enhancement. The goal is to compare different image processing methods for enhancing image quality or compressing images effectively.

## Features

- **Element-wise operations**: Brightness adjustment and color inversion.
- **Linear contrast adjustment**: Enhance the contrast of images using a linear contrast algorithm.
- **Global thresholding**: Apply simple and Otsu thresholding methods for image binarization.
- **Image loading and saving**: Users can load and save images in various formats (JPEG, PNG, etc.).
- **Interactive GUI**: The application features an intuitive and easy-to-use graphical interface created with Tkinter.

## How to Run

### Prerequisites

- Python 3.x
- Required Python packages(Tkinter, Pillow, OpenCV, NumPy)
  
### Running the Application
1. Clone the repository
2. Run the script in you IDE
3. The graphical interface will open, allowing you to load and process images.


# Theory

## Introduction
This project implements an image processing application using various techniques to enhance visual quality and transform images. The main methods implemented are:

- Pixel-wise operations (brightness increase, color inversion)
- Linear contrast stretching
- Global thresholding (simple threshold and Otsu's method)

## 1. Pixel-wise Operations

Pixel-wise operations are performed on each pixel of the image independently. In this project, two pixel-wise operations are implemented:

1. **Brightness Increase**: Adding a constant value to all pixels of the image, which increases the brightness.
    - $I'(x, y) = I(x, y) + C$, where $I(x, y)$ is the pixel intensity value, and $C$ is the added brightness.
    
2. **Color Inversion**: Inverting the intensity values of each pixel, resulting in a negative image.
    - $I'(x, y) = 255 - I(x, y)$

## 2. Linear Contrast Stretching

Linear contrast stretching (contrast enhancement) is used to improve the image by transforming the brightness range of the image to span the entire possible range [0, 255].

- The minimum and maximum intensity values of the original image are used for normalization:
- $I'(x, y) = \frac{I(x, y) - I_{\min}}{I_{\max} - I_{\min}} \times 255$
where $I_{\min}$ and $I_{\max}$ are the minimum and maximum intensity values respectively.

## 3. Global Thresholding

Global thresholding is used for image segmentation, where pixels are transformed into a binary image based on a given threshold.

1. **Simple Thresholding**: Applying a fixed threshold \( T \), where all pixel values above the threshold become white (255), and below the threshold become black (0):
\$
I'(x, y) = 
\begin{cases} 
255, & \text{if } I(x, y) \geq T \\
0, & \text{if } I(x, y) < T
\end{cases}
\$

2. **Otsu's Method**: An automatic threshold selection method that minimizes the intra-class variance (differences within each segment of the image).
    - The algorithm calculates the optimal threshold based on the intensity distribution of the pixels.

### Example
\[
T_{\text{Otsu}} = \arg\min_T \left( w_1(T) \sigma_1^2(T) + w_2(T) \sigma_2^2(T) \right)
\]
where \( w_1 \) and \( w_2 \) are the proportions of pixels below and above the threshold, and \( \sigma_1^2 \) and \( \sigma_2^2 \) are the variances of intensities in these segments.

## Comparison of Methods
- **Linear contrast stretching** helps improve the visual perception of the image, especially if the image has low contrast.
- **Global thresholding** works well for binarizing images, especially when dealing with clear objects on a uniform background.
