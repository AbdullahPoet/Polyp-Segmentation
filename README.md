# Medical Image Segmentation on Kvasir-SEG

## Overview

This repository contains deep learning models for **gastrointestinal polyp segmentation** using the **Kvasir-SEG dataset**. The goal is to accurately segment polyp regions from endoscopic images using state-of-the-art encoder-decoder architectures and transformer-based models.

---

## Dataset

**Kvasir-SEG**

- 1000 endoscopic polyp images with corresponding ground truth masks  
- Image size ranges from **332×487 to 1920×1072**  
- JPEG format images  
- Task: **Binary semantic segmentation (polyp vs background)**  

---

## Models Implemented

This project explores three different segmentation architectures:

### 1. U-Net++ (ResNet34 Encoder)
- Encoder: **ResNet34 (pretrained on ImageNet)**
- Architecture: Nested skip connections (U-Net++)
- Strength: Improved feature fusion across multiple decoder depths

---

### 2. Attention U-Net (Bottleneck Attention)
- Architecture: U-Net with **attention gates in bottleneck**
- Strength: Focuses on relevant spatial regions and suppresses background noise
- Best suited for irregular polyp shapes and low-contrast regions

---

### 3. Swin Transformer U-Net
- Encoder: **Swin Transformer** pretrained
- Architecture: Hybrid transformer + U-Net decoder
- Strength: Captures long-range dependencies and global context effectively
- Best performing on complex texture variations

---

## Training Setup

- Loss Functions: Dice Loss + BCE Loss 
- Optimizer: AdamW with Adaptive LR
- Learning Scheduler
- Input size: Resized images (typically 256×256 and 224x224)
- Augmentations:
  - Horizontal/vertical flips  
  - Rotation  
  - and more...
- Framework: PyTorch

---

## Evaluation Metrics

Model performance is evaluated using:

- Dice Coefficient  
- Intersection over Union (IoU)  
- Accuracy 


## Results Summary

| Model                     | Dice Score | IoU Score |
|--------------------------|------------|----------|
| U-Net++ (ResNet34)       | --         | --       |
| Attention U-Net          | --         | --       |
| Swin Transformer U-Net   | --         | --       |