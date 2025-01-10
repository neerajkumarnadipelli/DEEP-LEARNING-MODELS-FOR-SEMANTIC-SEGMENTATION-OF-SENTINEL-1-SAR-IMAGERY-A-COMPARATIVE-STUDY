# DEEP-LEARNING-MODELS-FOR-SEMANTIC-SEGMENTATION-OF-SENTINEL-1-SAR-IMAGERY-A-COMPARATIVE-STUDY

This repository contains a comparative study and implementation of state-of-the-art deep learning models for semantic segmentation of Sentinel-1 Synthetic Aperture Radar (SAR) imagery. The models include U-Net, Feature Pyramid Network (FPN), LinkNet, and Pyramid Attention Network (PAN). These models were evaluated using the BigEarthNet dataset for land cover classification tasks.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Models](#models)
- [Results](#results)


## Introduction

Semantic segmentation of SAR images involves partitioning radar imagery into distinct regions representing different land cover types or features. SAR data, characterized by its ability to capture backscatter intensities in all-weather and day-night conditions, presents unique challenges for segmentation due to noise and speckle effects.

This project explores the performance of four deep learning models:
- **U-Net**: A CNN architecture for image segmentation with a ResNet-34 encoder.
- **LinkNet**: Designed for efficient semantic segmentation using ResNet-34 as a backbone.
- **FPN**: Combines low-resolution and high-resolution feature maps for enhanced localization.
- **PAN**: Utilizes attention mechanisms to improve feature representation and segmentation boundaries.

The objective is to identify the most suitable architecture for SAR image segmentation based on metrics such as segmentation accuracy, robustness to noise, and computational efficiency.

## Dataset

The BigEarthNet dataset was used for training and evaluation, integrating data from Sentinel-1 SAR imagery (VV and VH polarization) and CORINE Land Cover (CLC) maps. The CLC reference maps were simplified from 44 classes to 5 major land cover types:
1. Urban Areas
2. Agriculture
3. Forests and Shrubs
4. Wetlands
5. Water Bodies

For more details, visit the [BigEarthNet](https://bigearth.net/) website.

## Models

### 1. U-Net
- Encoder: ResNet-34
- Input Shape: (128, 128, 2)
- Activation: Softmax for multi-class segmentation

### 2. LinkNet
- Encoder: ResNet-34
- Input Shape: (128, 128, 2)
- Efficient segmentation with skip connections

### 3. Feature Pyramid Network (FPN)
- Encoder: ResNet-34
- Input Shape: (128, 128, 2)
- Combines feature maps for contextual segmentation

### 4. Pyramid Attention Network (PAN)
- Encoder: ResNet-34
- Input Shape: (128, 128, 2)
- Attention-based refinement of segmentation boundaries


## Results

| Model   | Accuracy (%) | Inference Time (s) | Memory Usage (MB) |
|---------|--------------|-------------------|------------------|
| U-Net   | 84.67        | 9.06              | 174.98           |
| LinkNet | 84.50        | 6.82              | 216.65           |
| FPN     | 88.29        | 86.38             | 429.41           |
| PAN     | **88.98**    | 16.12             | **82.09**        |

PAN demonstrates the best accuracy and compact size, making it suitable for high-precision applications.

