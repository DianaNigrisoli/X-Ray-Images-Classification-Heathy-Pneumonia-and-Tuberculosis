# X-Ray-Images-Classification-Heathy-Pneumonia-and-Tuberculosis
Project of Applied AI in Biomedicine course at PoliMi - 2022

# Final Assignment: X-Ray Image Classification 

## Authors
- Meri Ferretti
- Diana Nigrisoli 
- Laura Pozzi 

---

# Repository Structure

This repository contains the notebooks, trained models, and dataset links used for the final assignment on X-ray image classification.

## Notebooks

### `Data_inspection.ipynb`
This notebook includes:
- Preliminary inspection of CSV files and images
- Image resizing
- Definition of Regions of Interest (ROIs) for preprocessing
- Histogram equalization analysis

### `Option_1.ipynb`
This notebook contains:
- Dataset creation for **Option 1**
- Two classification approaches:
  1. Transfer Learning + Fine-Tuning using **EfficientNetB3** with a custom fully connected classifier
  2. Feature extraction using **EfficientNetB3** followed by classification with a Machine Learning model

### `Option_2.ipynb`
This notebook contains:
- Dataset creation for **Option 2**
- Two classification approaches:
  1. Transfer Learning + Fine-Tuning using **EfficientNetB3** with a custom fully connected classifier
  2. Fine-Tuning of a CNN architecture proposed in the literature

### `Option_3.ipynb`
This notebook contains:
- Dataset creation for **Option 3**
- Transfer Learning + Fine-Tuning using **EfficientNetB3** with a custom fully connected classifier

### `XAI.ipynb`
This notebook contains the implementation and analysis of three Explainable AI (XAI) techniques:
- Grad-CAM
- LIME
- Occlusion

---
