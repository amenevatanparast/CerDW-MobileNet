# CerDW-MobileNet: Lightweight Fetal Cerebellum Segmentation in Ultrasound

## Overview
This repository contains the official implementation of **CerDW-MobileNet**, a lightweight deep learning framework for automated segmentation of the fetal cerebellum in ultrasound images, including both **normal anatomy** and **Dandy–Walker Malformation (DWM)** cases.

The model is specifically designed to address the challenges of fetal ultrasound imaging, including:

- Speckle noise
- Low contrast
- Weak or incomplete anatomical boundaries
- Structural variability in abnormal cases
- Limited dataset size

The framework combines efficient feature extraction with shape-aware refinement and multi-scale contextual learning, making it suitable for research and real-time clinical applications.

---

## Paper
If you use this work, please cite:

**A Lightweight Multi-Scale and Shape-Aware Framework for Cerebellar Segmentation in Normal and Dandy–Walker Fetal Ultrasound Images**

Authors:
- Amene Vatanparast
- Mansoor Fateh
- Hoda Mashayekhi
- Saideh Ferdowsi


---

## Dataset
The dataset used in this study includes:

- **200 normal fetal cerebellum ultrasound images**
- **80 Dandy–Walker abnormal cases**

Dataset sources include publicly available fetal ultrasound datasets, published clinical cases, and educational medical repositories.

Dataset access:

[Download Dataset]((https://drive.google.com/drive/folders/1EdDAOINKFETBUHY87XixCF8K1lixepA7?usp=drive_link))

---

## Model Architecture
CerDW-MobileNet consists of:

### 1. MLVUM Preprocessing
Maximum Local Variation-based Unsharp Masking for:

- Contrast enhancement
- Boundary sharpening
- Speckle noise reduction

### 2. MobileNetV3-Small Encoder
A lightweight backbone for efficient feature extraction.

### 3. Shape–Texture Refinement Module
Combines:
- Texture-sensitive convolutions
- Sobel edge extraction
- Boundary enhancement

### 4. Multi-Scale Context Module
Captures information at multiple receptive fields using dilated convolutions.

### 5. Attention Skip Fusion
Improves decoder reconstruction by selectively fusing encoder and decoder features.

---

## Performance
### Fetal Ultrasound Results

| Case Type | Accuracy | Dice Score |
|---------|----------|------------|
| Normal | 98.73% | 87.49% |
| Dandy–Walker | 97.93% | 78.50% |
| Average | 98.33% | 82.99% |

---

## Requirements
Install dependencies:

```bash
pip install tensorflow opencv-python numpy matplotlib scikit-image
