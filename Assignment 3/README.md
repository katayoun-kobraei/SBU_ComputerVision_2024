# Computer Vision Homework 3

## Theory questions:
## 1. Object Detection: Fast RCNN and Faster RCNN

### Fast RCNN
- **Overview**: An enhanced version of RCNN that improves both speed and accuracy by using a Region Proposal Network (RPN).

### Faster RCNN
- **Overview**: An extension of Fast RCNN that integrates RPN directly into the pipeline, eliminating external region proposal algorithms.
- **Loss Function** -  **RPN Classification Loss** - **RPN Regression Loss** - **Fast RCNN Classification Loss** - **Fast RCNN Regression Loss** 

---

## 2. Optical Flow Estimation

### Comparison of Optical Flow Algorithms
- **Lucas & Kanade** vs. **Horn & Schunck**
-  **Regularization Parameter (α) in Horn & Schunck**

### Aperture Problem
- **Definition**: A limitation where only the motion component perpendicular to an edge is observable through a small aperture, leading to ambiguities in motion estimation.
- **Impact**: Local methods struggle with complex motions, while global methods may mitigate ambiguities but are not infallible.
- **Strategies to Address**:
  1. **Global Methods**: Utilize global constraints to promote coherent flow fields.
  2. **Multi-Scale Approaches**: Capture motion across resolutions to counter small apertures.
  3. **Feature-Based Methods**: Track distinct features that provide reliable motion information.

# 3. Optical Flow Estimation and Vision Transformers

## a. Introduction to Optical Flow
## b. Optical Flow Estimation Techniques
## c. FlowNet Variants: FlowNetS and FlowNetC

### Common Refinement Process
Both models include an expanding part that uses "upconvolutional" layers to enhance the resolution of the estimated optical flow, allowing for higher fidelity predictions.

## 4. Vision Transformers (ViTs)
ViTs represent a transformative approach in computer vision, utilizing the self-attention mechanism. Key concepts include:

### Self-Attention Mechanism
- **Components**: Queries, Keys, and Values (Q, K, V) are computed for input features, allowing the model to weigh the importance of different parts of the input.
- **Processing**: Images are divided into patches, with position embeddings added to retain spatial information. The transformer encoder processes these patches using self-attention.

# Implementation Part

## Overview
This assignment focuses on various aspects of computer vision, involving object detection, motion estimation, speed prediction of moving vehicles, and image classification using vision transformers. Each question requires a different approach and methodology, and they will be tackled in sequential order.

### Question 1: Object Detection of Cats
In this question, the goal is to design a simple object detection model to identify cats in images, inspired by the architecture taught in class. The process includes:
1. **Data Preprocessing**: 
   - Read images and annotations.
   - Resize images to a fixed size of 416x416 pixels.
   - Normalize pixel values and bounding box coordinates.
   
2. **Model Architecture**:
   - Construct a feature pyramid network (FPN) to extract features from various stages of a ResNet-50 backbone.
   - Implement a detection head with two branches: one for bounding box regression and the other for class prediction.
   - Assemble the final model with a specialized FPN backbone and the detection head.

### Question 2: Lucas-Kanade Optical Flow
This question involves implementing the Lucas-Kanade method for estimating optical flow and motion analysis. The steps include:
- Understand that optical flow represents the motion of objects between consecutive frames.
- Assume the two consecutive frames are captured with negligible time difference, allowing for the simplification that motion is minimal and brightness remains relatively constant.
- Calculate motion using the Lucas-Kanade method, avoiding the use of pre-built libraries for this algorithm.

### Question 3: Speed Prediction of a Moving Vehicle
In this part, we will predict the speed of a moving vehicle using camera data under challenging lighting conditions. The approach involves:
- Utilizing CNNs with labeled images to predict speed.
- Avoid overfitting by employing appropriate input features.
- Generate a flow matrix from two consecutive frames of the video, which represents the change in position and speed of pixels.
- Store the direction and magnitude of changes in pixels using the HSV color channel.
- Train a custom architecture in PyTorch to estimate the speed of the vehicle and report the accuracy metrics of the model.

### Question 4: Image Classification Using Vision Transformers
The final question aims to utilize vision transformers for classifying images in the CIFAR-10 dataset. The steps include:
1. **Data Preprocessing**:
   - Resize images to 224x224 pixels and normalize pixel values.
   - Due to computational intensity, it is recommended to run this notebook on Google Colab.
   
2. **Model Implementation**:
   - Implement a vision transformer model using the PyTorch framework.
   - Train the vision transformer on the preprocessed dataset.
   - Compare the performance of the vision transformer with baseline models such as ResNet and VGG on the same dataset.

## Requirements
- Python 3.x
- PyTorch
- Libraries: NumPy, OpenCV, Matplotlib, etc.

## Setup Instructions
1. Clone this repository.
2. Install the required libraries if not already installed.
3. For Question 4, load the notebook in Google Colab for better performance due to computational needs.
4. Follow the instructions in each section of the notebook to complete the assignment.
