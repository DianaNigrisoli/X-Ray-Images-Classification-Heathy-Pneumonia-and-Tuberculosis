# Chest X-Ray Classification: Normal, Pneumonia, and Tuberculosis

A Python university project developed in **2022** for the **Applied AI in Biomedicine** course at **Politecnico di Milano**.

The project explores deep learning and machine learning approaches to classify chest X-ray images into three categories: **Normal**, **Pneumonia**, and **Tuberculosis**. It covers dataset inspection, image preprocessing, transfer learning, fine-tuning, and model interpretation through Explainable AI (XAI).

## Authors

- Meri Ferretti
- Diana Nigrisoli
- Laura Pozzi

---
## Project overview

The workflow compares three data preparation strategies and several classification approaches, with **EfficientNetB3 pretrained on ImageNet** as the main backbone. Particular attention is given to image quality, class imbalance, multiple images from the same patient, and text annotations that could influence predictions.

The original dataset contains **15,470 images from 12,086 patients**. Patient identities are kept separate across training, validation, and test sets to avoid overlap between splits.

## Repository contents

This repository contains the project notebooks, trained models, and dataset links.

| Notebook | Purpose |
| --- | --- |
| `Data_inspection.ipynb` | Explore the dataset and investigate preprocessing techniques |
| `Option_1.ipynb` | Build and evaluate the baseline approach |
| `Option_2.ipynb` | Train classifiers using one image per patient and standardized image polarity |
| `Option_3.ipynb` | Train a classifier using one image per patient and randomized image polarity |
| `XAI.ipynb` | Inspect model predictions using Grad-CAM, LIME, and occlusion |

## Notebooks

### `Data_inspection.ipynb`

Preliminary exploration of CSV metadata and images, including:

- Image resizing and inspection of image quality.
- Definition of background regions of interest (ROIs) for preprocessing analysis.
- Investigation of standard and inverted image polarity.
- Histogram analysis and equalization.

### `Option_1.ipynb` — Baseline

Uses the full dataset with median filtering as the baseline preprocessing strategy. Implements two classification approaches:

1. **Transfer learning and fine-tuning:** EfficientNetB3 with a custom fully connected classification head.
2. **Feature extraction and machine learning:** EfficientNetB3 features classified using Random Forest or AdaBoost.

### `Option_2.ipynb` — Standardized preprocessing

Uses **one image per patient** and a more extensive preprocessing pipeline:

- Resize images to `256 × 256 × 3`.
- Remove text annotations using **Keras-OCR** and **OpenCV inpainting**.
- Convert inverted images to standard radiological polarity.
- Apply median filtering to images identified as noisy.
- Apply histogram equalization and training-time data augmentation.

Implements EfficientNetB3 with a custom classification head, using transfer learning and fine-tuning, and an additional CNN architecture adapted from the literature.

### `Option_3.ipynb` — Randomized image polarity

Uses the same patient selection as Option 2, but replaces polarity standardization with **image inversion at a probability of 50%**, producing a mixture of standard and inverted images. The remaining preprocessing steps follow Option 2.

Classification uses EfficientNetB3 with a custom classification head, trained through transfer learning and fine-tuning.

### `XAI.ipynb` — Model interpretation

Applies three complementary techniques to investigate which image regions influence predictions:

- **Grad-CAM:** gradient-based heatmaps highlighting regions associated with a target class.
- **LIME:** local explanations based on predictions for perturbed versions of an image.
- **Occlusion:** systematic masking of image regions to measure changes in the model's output.

## Training and evaluation

The project includes class weighting to address class imbalance, early stopping, learning-rate reduction during fine-tuning, and evaluation using accuracy and class-specific F1 scores. Test-time augmentation is also explored by averaging predictions over transformed versions of each image.

## Getting started

The notebooks were developed in **Google Colab** using Python and Keras.

1. Open the notebooks in Google Colab or a compatible Jupyter environment.
2. Obtain the datasets and any saved models required by the selected notebook using the repository links.
3. Review the notebook's imports, dependency setup, and file paths before running it.
4. Start with `Data_inspection.ipynb`, then choose an `Option_*.ipynb` notebook for training and evaluation.
5. Use `XAI.ipynb` with the relevant trained model to explore its predictions.


Politecnico di Milano · Applied AI in Biomedicine · 2022
