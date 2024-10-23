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

1. **Simple Thresholding**: Applying a fixed threshold $T$, where all pixel values above the threshold become white (255), and below the threshold become black (0):
  $I'(x, y) = 255$ if $I(x, y) \geq T$, otherwise $I'(x, y) = 0$

2. **Otsu's Method**: An automatic threshold selection method that minimizes the intra-class variance (differences within each segment of the image).
    - The algorithm calculates the optimal threshold based on the intensity distribution of the pixels.

# Use Cases:

1. **Piecemeal Operations**

- **Image Enhancement**: Useful for improving local contrast or brightness in specific areas of an image.
- **Selective Filtering**: When certain regions of an image require different processing.
- **Custom Segmentation**: When specific features need to be isolated based on pixel value or neighborhood characteristics.

2. **Linear Contrast Stretching**

- **Low-Contrast Images**: Best suited for images where the intensity values are clustered in a narrow range.
- **Preprocessing for Analysis**: Useful before applying other image analysis techniques, such as segmentation or feature extraction, to ensure that details are more visible.
- **Medical Imaging**: Common in enhancing features in X-rays, MRIs, or other medical scans.
  
3. **Simple Thresholding**

- **Basic Segmentation**: Effective for applications where the foreground and background can be easily distinguished by intensity.
- **Image Binarization**: Useful in document processing, where text can be separated from the background.
- **Real-Time Applications**: Suitable for applications requiring fast processing and less computational complexity.
  
4. **Otsu’s Method**

- **Dynamic Range Images**: Ideal for images where the foreground and background have distinct intensity distributions but no predetermined threshold is available.
- **Complex Images**: Effective in scenarios with varying lighting conditions, shadows, or where the foreground and background are not easily separable.
- **Biological Imaging**: Commonly used in medical and biological image analysis to differentiate between cells and background in microscopy images.

# Comparison: Simple Thresholding vs. Otsu's Method

Simple Thresholding is the best for images with consistent backgrounds and clear object boundaries. So let's show it:
![house](https://github.com/user-attachments/assets/3ccd7535-2fb1-4898-8a76-f88850247dfd width="500" height="333")

![simple](https://github.com/user-attachments/assets/91213ea2-0b27-4db4-af61-2062c972a10d)

![otsu](https://github.com/user-attachments/assets/7d5642c5-658c-4aed-9a4a-eeecd2e7fcb1)
