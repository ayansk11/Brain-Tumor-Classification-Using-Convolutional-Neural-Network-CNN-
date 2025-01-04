# Brain-Tumor-Classification-Using-Convolutional-Neural-Network-CNN-
A deep learning project for classifying brain tumor MRI scans into multiple categories using a comprehensive dataset. The project focuses on automated tumor detection and classification using medical imaging data.


## Brain Tumor MRI Classification Dataset

This repository contains code for processing and analyzing a brain tumor MRI dataset with multiple tumor classifications.

## Dataset Description

The dataset consists of MRI scans categorized into different tumor types:
- Glioma
- Meningioma
- No tumor (notumor)
- Pituitary

**Dataset Statistics:**
- Training Images:
  - Glioma: 1321 images
  - Meningioma: 1339 images
  - No tumor: 1595 images
  - Pituitary: 1457 images

- Testing Images:
  - Glioma: 300 images
  - Meningioma: 306 images
  - No tumor: 405 images
  - Pituitary: 300 images

All images are standardized to 512x512 pixels in size.

## Setup and Installation

```bash
pip install kaggle
pip install Pillow
```

## Usage

The repository includes scripts for:
1. Downloading the dataset using Kaggle API
2. Extracting and organizing the dataset
3. Basic image processing and analysis
4. Dataset statistics calculation

## Code Structure

```python
# Download dataset
!kaggle datasets download masoudnickparvar/brain-tumor-mri-dataset

# Extract dataset
import zipfile
import os

# Count images in each category
def count_images(folder_path):
    image_counts = {}
    if not os.path.exists(folder_path):
        return image_counts
    
    for root, _, files in os.walk(folder_path):
        for file in files:
            if file.lower().endswith(('.png', '.jpg', '.jpeg', '.gif', '.bmp')):
                image_type = os.path.basename(root)
                image_counts[image_type] = image_counts.get(image_type, 0) + 1
    return image_counts
```

## Data Organization

The dataset is organized into two main directories:
- `/Training`: Contains training images
- `/Testing`: Contains testing images

Each directory contains subdirectories for different tumor types.


## Acknowledgments

Dataset source: Kaggle dataset by masoudnickparvar

