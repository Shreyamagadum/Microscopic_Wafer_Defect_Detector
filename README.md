# Microscopic_Wafer_Defect_Detector

## 🔬 Microscopic Wafer Defect Detection using ResNet-50

## 📌 Project Overview
This project focuses on building a **deep learning-based computer vision model** to automatically detect defective silicon wafers.

Using **transfer learning with ResNet-50**, the model classifies wafer images into:
- ✅ Healthy
- ❌ Cracked (Defective)

---

## 🎯 Objective
To develop a CNN-based system that:
- Detects wafer defects from microscopic images
- Uses image augmentation to improve dataset size
- Applies transfer learning for efficient training
- Performs real-time inference on new images

---

## 📂 Dataset Description

Dataset used:
- WM811K Silicon Wafer Map Dataset (Image version)

### 📊 Data Preparation
Original dataset contained multiple defect categories:
- Center, Donut, Edge Local, Edge Ring, Local, Near Full, Random, Scratch, None

### 🔄 Binary Conversion
To simplify classification:

- `None` → **Healthy**
- All other defect types → **Cracked**

Final structure:
- data/train/
  - healthy/
  - cracked/


---

## 🖼️ Image Augmentation (OpenCV)

To handle limited defective samples, the following augmentations were applied:

- Horizontal flipping  
- Rotation  
- Gaussian blur  

This increased dataset diversity and improved model generalization.

---

## ⚙️ Workflow

### 1. Data Preprocessing
- Organized dataset into `healthy` and `cracked` folders
- Resized images to 224x224

### 2. Data Loading
- Used PyTorch `ImageFolder` and `DataLoader`

### 3. Model Selection
- Used pretrained **ResNet-50**

### 4. Transfer Learning
- Froze all convolutional layers
- Replaced final fully connected layer

### 5. Model Training
- Loss function: CrossEntropyLoss
- Optimizer: Adam
- Trained for multiple epochs

### 6. Model Evaluation
- Monitored training loss

### 7. Inference
- Predicted labels for new wafer images
- Output: `Healthy` or `Cracked`

---

## 🧠 Model Architecture

- Backbone: ResNet-50 (pretrained)
- Modified final layer for binary classification

---

## 📈 Results

- Model successfully distinguishes between healthy and defective wafers
- Training loss decreased across epochs, indicating learning
- Performs real-time predictions on unseen images

---

## 🛠️ Tech Stack

- Python  
- PyTorch  
- Torchvision  
- OpenCV  
- PIL  

---

## 🚀 How to Run

1. Clone the repository
```bash
git clone https://github.com/your-username/wafer-defect-detector.git
```
2. Install dependencies
pip install torch torchvision opencv-python
3. Run training
jupyter lab
4. Run inference
python inference.py

---

📌 Future Improvements
Add validation dataset and accuracy metrics
Implement confusion matrix
Fine-tune deeper layers of ResNet
Deploy using Streamlit (UI)

---

👨‍💻 Author
Shreyash Magadum

---

⭐ Acknowledgment

This project was developed as part of a deep learning assignment focused on wafer defect detection using transfer learning and CNNs.
---
