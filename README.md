# Environment Perception for Self-Driving Cars

![Environment Perception for Self-Driving Cars](media/cover.gif)


This project demonstrates key components of environment perception in self-driving cars using computer vision and 3D data processing techniques. It focuses on detecting and understanding the drivable space, ground plane estimation, and semantic segmentation from sensor data.

---

## Project Overview

Self-driving cars rely heavily on environment perception to navigate safely and efficiently. This project implements fundamental perception tasks such as:

- Ground plane estimation from 3D point clouds or depth data
- Semantic segmentation of road scenes to identify drivable space and obstacles
- Lane and obstacle detection using image and sensor fusion

These tasks collectively help the autonomous vehicle understand its surroundings to make safe driving decisions.

---

## Notebook Structure

The notebook is organized into **three main sections**, each focusing on a critical aspect of environment perception:

### 1. **Ground Plane Estimation**
- Objective: Fit a plane model to 3D point cloud data to identify the ground surface.
- Techniques: RANSAC algorithm is used for robust plane fitting by rejecting outliers.
- Outcome: The equation of the ground plane is computed, enabling filtering of points close to this plane.

### 2. **Semantic Segmentation and Drivable Space Estimation**
- Objective: Use semantic segmentation neural network outputs to classify pixels into categories such as road, lane markings, vehicles, and pedestrians.
- Techniques: Deep learning models for pixel-wise classification, followed by spatial filtering.
- Outcome: Drivable areas are extracted by thresholding semantic labels, creating a mask that highlights safe driving regions.

### 3. **Lane and Obstacle Detection**
- Objective: Detect lane lines and obstacles within the segmented drivable space.
- Techniques: Image processing methods such as edge detection, Hough transform for line detection, and clustering for obstacles.
- Outcome: Lane boundaries and obstacles are detected, allowing for path planning and collision avoidance.

---

## Flow Diagram

```plaintext
+------------------------+          +------------------------------+          +-----------------------------+
|                        |          |                              |          |                             |
| 1. Ground Plane         |  ---->   | 2. Semantic Segmentation     |  ---->   | 3. Lane & Obstacle          |
|    Estimation           |          |    & Drivable Space Estimation|          |    Detection                |
|                        |          |                              |          |                             |
+------------------------+          +------------------------------+          +-----------------------------+

Input: 3D Point Cloud or Depth Data
Output: Ground Plane Equation      Output: Drivable Space Mask           Output: Detected Lane Lines & Obstacles
