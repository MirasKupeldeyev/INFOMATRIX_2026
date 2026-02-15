# Deepfake Video Detection

Deep learning system for detecting deepfake videos using frame-based CNN classification.  
The model classifies videos as **REAL** or **FAKE** by extracting multiple frames and averaging predictions.

---

## Overview

This project implements a deepfake detection pipeline using:

- PyTorch  
- timm (PyTorch Image Models)  
- EfficientNet-B3 (pretrained)  
- OpenCV for frame extraction  

Each video is sampled into 16 frames. Frames are processed independently by the CNN, and predictions are averaged to produce the final decision.

---

## Dataset Structure
