# HairXNet – Hair Disease Classification using Deep Learning

HairXNet is a deep learning-based project that classifies **14 different hair and scalp diseases** using **Transfer Learning** with the **Xception architecture**.  
This project aims to support dermatologists and researchers by providing an automated tool for preliminary diagnosis of hair-related disorders.

🔗 **Full Code & Notebook:** [Kaggle Notebook](https://www.kaggle.com/code/masud1105/hair-diseases-classification-model)

---

## 📌 Introduction
Hair and scalp disorders affect millions worldwide, causing both **physical discomfort** and **psychological stress**.  
Traditional diagnosis requires **clinical expertise**, but with the advancement of **Deep Learning** and **Computer Vision**, automated systems can assist in **early detection** and **decision-making**.  

HairXNet leverages **Xception (pre-trained on ImageNet)** as a feature extractor and fine-tunes additional layers to classify images into **14 categories of hair diseases**.

---

## 📂 Dataset
- **Source:** Kaggle Hair Disease Dataset  
- **Classes:** 14 hair/scalp conditions  
- **Train Set:** 211 images  
- **Test Set:** 59 images  
- **Image Size:** Resized to `299×299 px`  
- **Preprocessing:** Rescaling + Data Augmentation (rotation, zoom, horizontal flip)  

### Disease Classes
1. Acne Keloidalis  
2. Alopecia Areata  
3. Androgenic Alopecia  
4. Discoid Lupus  
5. Dissecting Cellulitis  
6. Folliculitis Decalvans  
7. Hirsutism  
8. Hot Comb Alopecia  
9. Lichen Planopilaris  
10. Pseudopelade  
11. Telogen Effluvium  
12. Trichorrhexis Nodosa  
13. Trichotillomania  
14. Tufted Folliculitis  

---

## 🏗️ Model Architecture
- **Base Model:** Xception (pre-trained on ImageNet, `include_top=False`)  
- **Input Size:** `299 × 299 × 3`  
- **Custom Layers:**  
  - GlobalAveragePooling2D  
  - Dense(1024, activation='relu')  
  - Dense(14, activation='softmax')  
- **Frozen Layers:** All base model layers frozen  

---

## ⚙️ Training Configuration
- **Loss Function:** Categorical Crossentropy  
- **Optimizer:** Adam (lr = 0.001)  
- **Epochs:** 30  
- **Batch Size:** 32  
- **Metrics:** Accuracy  

---

## 📊 Results
- **Training Accuracy:** 98.58%  
- **Validation Accuracy:** 72.88%  
- **Training Loss:** 0.0464  
- **Validation Loss:** 1.1636  

> The model demonstrates strong training performance but moderate generalization due to limited dataset size and class imbalance.  

---

## 🚀 Future Improvements
- Expand dataset size for better generalization  
- Apply fine-tuning of deeper layers in Xception  
- Experiment with ensemble models (e.g., EfficientNet, ResNet)  
- Deploy model as a web app for dermatology assistance  

---

## 🧑‍💻 Author
**Mohammed Masud Chowdhury Mahir**  
🎓 Department of Computer Science & Engineering, UITS  
📎 [Kaggle Profile](https://www.kaggle.com/masud1105)

---

## 📜 License
This project is open-source and available under the **MIT License**.
