# ✈️ Aircraft Damage Detection & Captioning

🚀 An intelligent dual-stage system that detects aircraft damage and generates human-like inspection reports using Deep Learning + Vision-Language Models.

---

## 🔍 Overview

Aircraft inspection is critical for safety, but manual analysis is time-consuming and error-prone.

This project automates the process by combining:

- 🧠 Computer Vision (CNN) for damage classification  
- 🗣️ Vision-Language Models (VLM) for descriptive reporting  

💡 The system not only detects damage but also explains it in natural language, making it highly useful for inspectors and maintenance teams.

---

## ✨ Key Features

### ✅ Damage Classification
- Detects aircraft surface defects  
- Classifies into:
  - 🔸 Dent  
  - 🔹 Crack  

### ✅ Image Captioning
- Generates general descriptions of aircraft images  

### ✅ Damage Summarization
- Produces detailed, technical explanations of detected damage  

---

## 🧠 Model Architecture

### 🔹 1. Classification Model
- **Base Model:** VGG16 (pre-trained on ImageNet, frozen layers)  
- **Custom Head:**
  - Flatten  
  - Dense (512, ReLU)  
  - Dropout (0.3)  
  - Dense (512, ReLU)  
  - Dropout (0.3)  
  - Output (Sigmoid)  

- ⚙️ Optimizer: Adam (LR = 0.0001)  
- 📉 Loss Function: Binary Crossentropy  

---

### 🔹 2. Captioning & Summarization
- **Model:** BLIP (Bootstrapping Language-Image Pretraining)  
- Integrated via custom Keras layer:  
  `BlipCaptionSummaryLayer`

📌 Supports:
- Caption Mode → General description  
- Summary Mode → Detailed inspection-level explanation  

---

## ⚙️ Tech Stack

### 🚀 Core Technologies
- Python  
- TensorFlow / Keras  
- Deep Learning  
- Computer Vision  

### 📚 Libraries & Tools
- NumPy  
- OpenCV  
- Matplotlib  
- Transformers (Hugging Face)  

---

## ☁️ Workflow

### 1️⃣ Data Preparation
- Dataset auto-downloaded & extracted  
- Augmentation using `ImageDataGenerator`  

### 2️⃣ Model Training
- Train VGG16-based classifier  

### 3️⃣ Inference Pipeline
- Input aircraft image  
- Predict damage type  
- Generate:
  - Caption 📝  
  - Summary 📄  

---

## 📊 Results

- 📌 **Classification Accuracy:** ~70%

### 🧾 Sample Outputs

**Caption:**
```
this is a picture of a plane
```

**Summary:**
```
this is a detailed photo showing the damage to the fuselage of the aircraft
```

---

## 🚀 How to Use

### 🔧 Setup
```bash
pip install -r requirements.txt
```

### ▶️ Run
1. Train the classification model  
2. Use the helper function:

```python
generate_text(image_path, mode="caption")   # or "summary"
```

---

## 💡 Future Improvements

- 🔼 Improve accuracy using fine-tuning (unfreeze VGG16 layers)  
- 🧠 Try advanced models like EfficientNet / ViT  
- 📊 Add bounding box localization (object detection)  
- 📝 Improve caption quality using BLIP-2 or GPT-based VLMs  

---

## 🤝 Contributing

Contributions are welcome!  
Feel free to fork the repo, improve it, and submit a PR.

---

## 📌 Author

👤 **Manab Barman**

---
