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

### Supported formats

**Videos:** `.mp4`, `.avi`, `.mov`, `.mkv`  
**Images:** `.jpg`, `.png`, `.jpeg`

---

## Model Architecture

- **Backbone:** EfficientNet-B3 (pretrained)  
- **Output classes:** 2 (REAL / FAKE)  
- **Loss:** CrossEntropyLoss  
- **Optimizer:** AdamW  
- **Scheduler:** ReduceLROnPlateau  
- **Early stopping:** based on ROC-AUC  

---

## Training

### Key parameters

- Frames per video: 16  
- Batch size: 4  
- Epochs: 20  
- Image size: 224×224  

### Data augmentation

- Resize  
- Horizontal flip  
- Color jitter  
- Normalization (ImageNet statistics)  

---

## Evaluation Metrics

- Accuracy  
- ROC-AUC  

ROC-AUC is used as the primary metric for model selection.

---

## Inference
Prediction: FAKE
Confidence: 87.34%
