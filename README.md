# Driver Drowsiness Detection System (DrowsyNet) 🚗💤

This project explores a hybrid machine learning approach for real-time driver fatigue detection, developed as a collaborative team project in 2025. The goal is to combine deep learning with rule-based logic to build a system that behaves reliably in safety-aware scenarios.

---

## 📌 Project Motivation

My main interest lies in **Data Science and Machine Learning**, particularly in understanding how models behave beyond raw accuracy metrics.  
In this project, the focus was not only on classification performance, but also on:

- data behavior and class imbalance,
- model assumptions,
- temporal consistency in predictions,
- and reducing brittle, frame-based decisions.

Computer Vision is used here as an application domain rather than a standalone goal.

---

## 🧠 Model Architecture: DrowsyNet

At the core of the system is **DrowsyNet**, a lightweight CNN designed for real-time inference.

- **Backbone:** MobileNetV2, chosen for its balance between accuracy and computational efficiency  
- **Transfer Learning:** Pre-trained weights with a fine-tuned classification head  
- **Hybrid Logic:** CNN probability outputs combined with Eye Aspect Ratio (EAR) heuristics  
- **Temporal Reasoning:** Sliding window analysis to detect sustained fatigue patterns and reduce false positives

---

## ⚙️ Training & Optimization

To ensure stable convergence and generalization, the following strategies were applied:

- **Bayesian Optimization:** Used to tune learning rate, weight decay, and dropout parameters  
- **Dataset Size:**  
  - 35,997 training samples  
  - 8,940 validation samples  
- **Data Augmentation:** Random rotations, horizontal flips, and color jittering to improve robustness

---

## 📈 Performance Summary

- **Validation Accuracy:** 93.06%  
- **F1-Score:** 0.93 (balanced across alert and drowsy classes)  
- **Drowsy Class Metrics:**  
  - Precision: 0.94  
  - Recall: 0.93  

These results emphasize consistency and reliability rather than single-metric optimization.

---

## ⚠️ Real-Time Alert Logic

Instead of relying on single-frame predictions, the system applies a time-based warning mechanism:

1. **3 seconds:** “Take a short break” reminder  
2. **6 seconds:** “Serious alert – pull over immediately” warning  

This design prioritizes safety and reduces unnecessary alerts caused by brief eye closures.

---

## 🛠️ Tech Stack

- **Deep Learning:** PyTorch, Torchvision  
- **Computer Vision:** OpenCV, MediaPipe Face Mesh  
- **Data & Analysis:** NumPy, Pandas, Scikit-learn, Matplotlib  
- **Environment:** Google Colab

---

## 📄 Project Report

A detailed project report covering the dataset, model design choices, and experimental setup is included in this repository for readers who want to explore the technical details further.

- 📘 **[Driver_Drowsiness_Detection_Report.pdf](./Driver_Drowsiness_Detection_Report.pdf)**

---
## 🤝 Acknowledgments

This project was developed collaboratively by **Sümeyye Karaman**, **Şevval Aydoğan**, and **Seray Üstün**.
