# ImageMaster: Image Processing and Compression

## Description

**ImageMaster** is a Python-based graphical user interface (GUI) application that allows users to perform various image processing tasks. The project implements element-wise operations, linear contrast adjustments, and global thresholding methods for image compression and enhancement. The goal is to compare different image processing methods for enhancing image quality or compressing images effectively.

## Features

- **Element-wise operations**: Brightness adjustment and color inversion.
- **Linear contrast adjustment**: Enhance the contrast of images using a linear contrast algorithm.
- **Global thresholding**: Apply simple and Otsu thresholding methods for image binarization.
- **Image loading and saving**: Users can load and save images in various formats (JPEG, PNG, etc.).
- **Interactive GUI**: The application features an intuitive and easy-to-use graphical interface created with Tkinter.

## Methods Implemented

1. **Brightness Adjustment**:
   - Increase or decrease the brightness of an image using an element-wise operation.
   
2. **Invert Colors**:
   - Apply color inversion to the loaded image.

3. **Linear Contrast Adjustment**:
   - Enhance the contrast of the image by stretching pixel values to a specific range.
   
4. **Global Thresholding**:
   - **Simple Threshold**: Converts grayscale images to binary using a fixed threshold value.
   - **Otsu's Thresholding**: A more advanced global thresholding method that automatically determines the optimal threshold.

## GUI Features

- **Load Image**: Load an image from your local file system.
- **Brightness Adjustment**: Input a value (-255 to 255) to increase or decrease the brightness of the image.
- **Invert Colors**: Apply color inversion to the image.
- **Linear Contrast**: Automatically adjusts the image's contrast using linear scaling.
- **Thresholding**: Apply global thresholding techniques (simple or Otsu) to the image.
- **Save Image**: Save the processed image in the desired format.

## How to Run

### Prerequisites

- Python 3.x
- Required Python packages

