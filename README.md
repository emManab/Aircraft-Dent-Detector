# Aircraft Damage Detection & Captioning

## ✨ Project Overview
This project implements a dual-stage automated system for aircraft maintenance and safety inspection. It combines computer vision for classification with advanced Vision-Language Models (VLM) for descriptive reporting.

### ✅ Key Features
1.  **Damage Classification:** Automates the detection of aircraft surface defects, specifically classifying them into **'dent'** and **'crack'** categories using Deep Learning.
2.  **Image Captioning:** Generates natural language descriptions of identified damage using the BLIP model.
3.  **Damage Summarization:** Provides detailed summaries of localized damage to assist inspectors in reporting.

## ⚙ Technical Stack
- **Deep Learning Frameworks:** 
    - **TensorFlow/Keras:** Used for the classification model and custom layer integration.
    - **PyTorch:** Backend for the Hugging Face Transformers models.
- **Architectures:** 
    - **VGG16:** Pre-trained on ImageNet, used as a feature extractor for the classification task.
    - **BLIP (Bootstrapping Language-Image Pretraining):** Utilized for generating image captions and summaries.
- **Data Processing:** 
    - **Keras ImageDataGenerator:** For real-time data augmentation and normalization.
    - **PIL (Pillow):** For image handling and processing.
- **Libraries:** `transformers`, `numpy`, `matplotlib`, `tarfile`.

## ☁ Model Architecture

### 1. Classification Model
- **Base:** VGG16 (frozen layers).
- **Head:** 
    - Flatten layer
    - Dense Layer (512 units, ReLU)
    - Dropout (0.3)
    - Dense Layer (512 units, ReLU)
    - Dropout (0.3)
    - Final Dense Layer (1 unit, Sigmoid activation)
- **Optimizer:** Adam (LR=0.0001)
- **Loss:** Binary Crossentropy

### 2. Captioning & Summarization
- Uses a custom **Keras Layer** (`BlipCaptionSummaryLayer`) that wraps the `Salesforce/blip-image-captioning-base` model.
- Supports two tasks: `caption` (broad description) and `summary` (detailed technical description).

## ⚖ How to Use
1.  **Environment Setup:** Install requirements using the provided shell commands in the notebook.
2.  **Dataset:** The notebook automatically downloads and extracts the Aircraft Damage Dataset.
3.  **Training:** Run the classification section to train the VGG16-based model.
4.  **Inference:** Use the `generate_text` helper function to process any aircraft damage image for automated description.

## ⌛ Results
- **Classification Accuracy:** Achieved ~70% on test data using frozen VGG16 features.
- **VLM Output Examples:** 
    - *Caption:* "this is a picture of a plane"
    - *Summary:* "this is a detailed photo showing the damage to the fuselage of the aircraft"

---
