# Second Assignment

### Instructor: Dr. Ahmad Modi  
---

## Overview

This assignment covers various foundational concepts in image processing and computer vision, focusing on edge detection, corner detection, feature extraction, and object detection. The tasks are designed to help you understand different filtering techniques, corner detection algorithms, and how classical methods like SIFT and HOG are used for feature matching. You will also work with a CNN-based model for object detection.

---

## Theoretical Questions (20 points)

### **Problem 1 (5 points)**  
**Objective**: Analyze and explain the use of different kernels (filters) and their effects on an image (Lena image).  
**Tasks**:
- Identify the purpose and effects of four different kernels.
- Explain the differences between these kernels and their applications in image processing.
- Match each kernel to the corresponding output image.

### **Problem 2 (5 points)**  
**Objective**: Compare the Laplacian filter with Sobel and Canny filters for edge detection.  
**Tasks**:
- Provide three reasons why the Laplacian filter is not as effective as Sobel and Canny for edge detection.
  
### **Problem 3 (10 points)**  
**Objective**: Understand the Harris Corner Detection algorithm.  
**Tasks**:
- Explain the Harris Corner Detection process.
- Analyze the relationship between matrix \(M\), image gradients \(I_x\), and \(I_y\).
- Calculate and determine whether the region in a provided image is an edge, corner, or smooth area based on the Corner Response Measure.

### **Problem 4 (10 points)**  
**Objective**: Implement the Canny edge detector on a grayscale image.  
**Tasks**:
- Apply the Canny edge detection algorithm using custom parameters (instead of Gaussian and Sobel filters).
- Provide the final output image and explain each step of the process.

---

## Practical Coding Questions (80 points)

### **Problem 1 (12 points)**
**Objective**: Image Enhancement and Edge Detection  
**Tasks**:
- Increase the resolution of an image using an appropriate method.
- Extract edges from two provided images using the Sobel edge detector.
- Enhance details in two given images.
- Implement automatic thresholding in the Canny edge detection algorithm based on the input image.

### **Problem 2 (15 points)**  
**Objective**: Detect Road Lane Lines in Driver POV Images  
**Tasks**:
- Use classical image processing techniques (e.g., Hough Transform) to detect road lane lines from the provided driver’s point of view images.

### **Problem 3 (23 points)**  
**Objective**: Feature Matching Using HOG and SIFT  
**Tasks**:
- Use HOG (Histogram of Oriented Gradients) and SIFT (Scale-Invariant Feature Transform) algorithms to detect matching features between a reference image and several cropped images.
- For each cropped image, determine if it is part of the original image and highlight the matched section.
- Discuss the advantages of SIFT over HOG and the types of transformations each algorithm can handle.

## Implementation Part
### Q1
This question performs various image processing techniques using OpenCV, NumPy, and Matplotlib. The main tasks include filtering, enhancing, and detecting edges in images.

#### Key Sections:

1. **Image Filtering and Sharpening**:
   - Loads and displays the original image.
   - Applies multiple sharpening filters (basic, simple, strong) to enhance details.
   - Uses Sobel filters for edge detection and a Laplacian filter to emphasize edges.
   - Implements unsharp masking for additional sharpness.
   - Displays all processed images for comparison.

2. **Edge Detection**:
   - Loads two grayscale images and applies Sobel filters for horizontal and vertical edge detection.
   - Uses Laplacian filtering with thresholding to enhance edge visibility.
   - Implements Canny edge detection with automatic thresholding.
   - Shows original and filtered images side-by-side.

3. **Image Enhancement**:
   - Loads two color images, applies Gaussian blur to reduce noise.
   - Applies sharpening filters and enhances contrast using scaling.
   - Conducts histogram equalization in the YUV color space for improved brightness and contrast.
   - Displays the original, blurred, sharpened, and equalized images.

Certainly! Here’s a more concise summary of the provided code for processing images using OpenCV, particularly focusing on line detection using the Hough Transform:

---

### Q2

This question  is about implementing image processing techniques to detect and draw lines in images using OpenCV, NumPy, and Matplotlib. 

#### Key Steps:

1. **Image Loading and Visualization**:
   - Loads images using `matplotlib.image` and displays them.

2. **Region of Interest (ROI)**:
   - Defines a polygonal region of interest to focus on specific areas of the image.
   - Uses a masking technique to isolate this region.

3. **Edge Detection**:
   - Converts images to grayscale.
   - Applies Canny edge detection to identify edges within the cropped region.

4. **Line Detection**:
   - Utilizes the Hough Transform (`cv2.HoughLinesP`) to detect lines in the processed edge image.
   - Adjusts parameters like `rho`, `theta`, `threshold`, `minLineLength`, and `maxLineGap` to optimize line detection.

5. **Line Drawing**:
   - Draws the detected lines back onto the original image using a specified color and thickness.
   - Displays the original image with detected lines overlayed.

6. **Batch Processing**:
   - Processes multiple images (input1.jpg to input6.jpg) in a loop, displaying the processed results for each.


### Q3

#### Key Steps:

Implementing template matching using SIFT and HOG looks well-structured and covers a comprehensive range of techniques for detecting and matching image features. 

### Summary of Code Components

1. **Loading Images**: The original image and several cropped templates are loaded into memory.

2. **Gray Conversion**: All images are converted to grayscale for feature detection.

3. **SIFT Detection and Matching**:
   - Implementing a function `detect_and_draw` that:
     - Initializes SIFT to detect key-points and compute descriptors for both the original and cropped images.
     - Matches descriptors using both BFMatcher and FLANN-based matcher.
     - Applies Lowe's ratio test to filter good matches.
     - Finds homography to draw bounding boxes around detected features in the original image.
     - Displays the cropped image, feature matches, and the original image with the bounding box.

4. **HOG Template Matching**:
   - The function `hog_template_matching` computes HOG features for the target and template images.
   - It slides a window across the target image to compute dot products with the HOG features of the template to find the best match location.
   - Displays the original image with the matched template and the template itself.

### Advantages of SIFT

- **Robustness to Changes**: 
  - **Scale, Rotation, and Translation**: SIFT is invariant to these transformations, allowing it to detect the same features even if they appear in different sizes, orientations, or positions in the image.
  
- **High Accuracy**: 
  - It detects distinctive features that are highly repeatable, which enhances matching reliability across images.

### Advantages of HOG

- **Computational Efficiency**: 
  - HOG is simpler and faster in feature extraction compared to SIFT, making it suitable for real-time applications.

- **Object Detection**:
  - HOG excels at capturing the shape and structure of objects by analyzing the spatial distribution of gradient orientations.

### Resilience to Changes

- **SIFT**: 
  - Highly resilient to scale, rotation, and translation changes. It performs well in environments with variable lighting and perspective distortions.

- **HOG**: 
  - While it can handle scale changes, it is primarily effective for detecting objects based on shape and orientation. It may struggle with precise keypoint localization under significant transformations.

---

Good luck, and feel free to reach out if you have any questions!
