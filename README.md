# Aerial Image Semantic Segmentation using U²-Net

A Keras/TensorFlow implementation of the U²-Net (U-squared-Net) architecture for semantic segmentation of buildings from high-resolution aerial imagery.

****

---

## Overview

This project implements the U²-Net model, a nested U-structure designed for salient object detection, and adapts it for a binary semantic segmentation task (building vs. non-building). The model is trained on the "Aerial Imagery for Roof Segmentation" dataset.

### Key Features
* **Model:** A complete implementation of the U²-Net architecture from scratch.
* **Data Handling:** Uses `patchify` to break down large aerial images into smaller, manageable patches for training.
* **Metrics:** Implements and tracks Intersection over Union (IoU) and Dice Coefficient as custom metrics.
* **Prediction:** Includes logic to load the trained model, predict on new test images, and visualize the results.

---

## Tech Stack

![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=keras&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3776AB?style=for-the-badge&logo=matplotlib&logoColor=white)

---

## Model Architecture

The U²-Net is a novel two-level nested U-structure. 
* The outer level is a large U-Net that captures high-level context.
* Each stage of this outer U-Net is filled by another smaller U-Net (the nested "ReSidual U-block" or RSU), which captures more granular, local features.

This design allows the model to capture rich multi-scale features without significantly increasing the computational cost.

---

## How to Use

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/mahdifelfeli/u2net_model.git](https://github.com/mahdifelfeli/u2net_model.git)
    cd u2net_model
    ```

2.  **Create a virtual environment and install dependencies:**
    ```bash
    # Create environment
    python -m venv venv
    # Activate (Windows)
    .\venv\Scripts\activate
    # Activate (macOS/Linux)
    source venv/bin/activate
    
    # Install libraries
    pip install -r requirements.txt
    ```

3.  **Download the Dataset:**
    * The model is trained on the "Aerial Imagery for Roof Segmentation" dataset.
    * Run the following command (or the cell in the notebook) to download it:
    ```bash
    pip install gdown
    gdown --id 16-j12-i0i-eM-M3p-1-b-J-z-p-q-y-q
    ```
    * This will download `Aerial_Image_Dataset.zip`. Unzip it in the main project directory.

4.  **Run the Notebook:**
    * Open and run the `Aerial_Semantic_Segmentation_u2net.ipynb` notebook:
    ```bash
    jupyter notebook
    ```
