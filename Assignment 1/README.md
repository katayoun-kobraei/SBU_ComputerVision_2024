# Computer Vision Assignment - First Assignment

Welcome to the Computer Vision First repository for the Winter 2023 course at Shahid Beheshti University. This assignment is designed to help you understand various concepts of image processing and computer vision by working with different color spaces, image transformations, and practical applications of the theories discussed in the course.

---

## Exercise Overview

### **Exercise 1 - Luminance vs. Brightness (5 points)**
Did some Research on the concepts of **Luminance** and **Brightness**. Explaining how they differ and express your interpretation of the image provided. Discussed whether these two concepts are related to the image or not.

### **Exercise 2 - Color Conversion (10 points)**

Given the RGB color `COLOR = (251, 151, 51)`:

1. Converting this color to **CMYK** representation. (2 points)
2. Converting it to **YIQ** color space. (2 points)
3. Using the transformation matrix to convert it to **YCbCr**. (2 points)
4. Did Research and briefly explained the use cases of each color space (CMYK, YIQ, YCbCr). Compare their advantages and when one is more effective than another. (4 points)

### **Exercise 3 - Probability Transformation (5 points)**

Given an image with intensity values `r` in the range [0,1] with the probability distribution \(p_r(r)\), which is shown in a given plot. Transforming the intensity levels of the image such that the resulting distribution follows \(p_z(z)\) (Assume continuous values). Deriving the transformation that performs this mapping using `r` and `z`.

### **Exercise 4 - Image Histogram Operations (10 points)**

1. Applying **Histogram Equalization** on the given grayscale image with intensity levels in the range [0,7]. Show the final image and explain the steps. (5 points)
2. Performing **Bit Plane Slicing** and display the result. (3 points)
3. Enhancing the contrast of the image and show the result. (2 points)

### **Computer-Based Questions (80 points)**

The goal is to familiarize us with image manipulation using Python libraries like OpenCV, covering the topics up to the third slide of the course.

1. **Basic Image Manipulations (20 points)**  
   a) Reading and displaying **Image 1**.  
   b) Displaying the RGB channels of the input image.  
   c) Converting the image to grayscale and binary without using built-in functions.  
   d) Converting the image's RGB space to **HSV** without using built-in functions.  
   e) Comparing our HSV conversion with OpenCV's `cvtColor` function.  
   f) Investigating and implementing red color extraction from the image using HSV.

2. **Histogram Matching (5 points)**  
   Implementing histogram matching for **Image 2.1** to match the histogram of **Image 2.2**. 

3. **Filtering Comparison (15 points)**  
   a) Applying a **3x3 average filter** twice, a **9x9 average filter**, and a **5x5 Gaussian filter** to an image. Comparing the histograms of the resulting images and explain if any of the filters are equivalent.  
   b) If none of the filters are equivalent, we will find an alternative filter that achieves the same effect as two consecutive 3x3 average filters.  
   c) Comparing the filtered images using **PSNR** and discuss what can be inferred from the results.

4. **Manual Histogram Equalization (7 points)**  
   Implementing histogram equalization without using OpenCV or Pillow libraries for **Image 4**. Comparing the result with that of the built-in libraries.

5. **Noise Removal (3 points)**  
   Removing the noise from **Image 5** as effectively as possible. Explaining our approach.

6. **Unsharp Masking (10 points)**  
   Implementing **Unsharp Masking** on a chosen image. Generating a blurred version of the image, subtracting it from the original, and adding back the result with a suitable coefficient to sharpen the image.

7. **Star Detection (15 + 5 points)**  
   Detecting stars in 8 given real images of the night sky. our program should:
   - Count the number of stars visible to the human eye.
   - Print the coordinates of at least one detected star.
   - Visualize the contour of the detected stars in the original image.

---

Good luck, and happy coding!
