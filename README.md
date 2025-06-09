# 🌿 Crop Disease Detection using EfficientNetB4

> A CNN-based computer vision model for detecting plant leaf diseases from RGB images, achieving **95.69% test accuracy** across 39 crop disease classes. Built using **EfficientNetB4** and optimized for both accuracy and performance.

📦 Dataset: [PlantVillage (Mendeley)](https://data.mendeley.com/datasets/tywbtsjrjv/1)
🚀 Live Demo: [Streamlit App](https://hackathonpavaman.streamlit.app/)

---

## 🔍 Hackathon Project Submission Checklist ✅

### ✅ Model Code and Working

* Full training workflow implemented using TensorFlow/Keras.
* Dataset loading, augmentation, and splitting.
* Two-phase training:

  * Stage 1: Frozen base training (6 epochs)
  * Stage 2: Fine-tuning top layers (10 epochs)
* Output: `.keras` model saved for deployment.

📁 Code: [`Plant Disease Model Training.ipynb`](https://colab.research.google.com/drive/1ITgvDcMNlcwNMoq2f-43n4wl81q4xvXv)

---

### 🧠 Model Architecture

| Component      | Detail                               |
| -------------- | ------------------------------------ |
| 📦 Base Model  | EfficientNetB4 (ImageNet weights)    |
| 🖼️ Input Size | 160 × 160 × 3                        |
| 🧠 Layers      | GlobalAveragePooling, Dropout, Dense |
| 🧪 Output      | Softmax (39 classes)                 |
| ⚙️ Params      | \~19 million total                   |

---

### 📄 Why EfficientNetB4?

EfficientNetB4 was chosen for:

* ⚖️ Superior **accuracy-to-efficiency** trade-off
* 🚀 Faster convergence with **ImageNet pretraining**
* 📱 Lightweight for **mobile or edge deployment**
* 🔁 Compound scaling of width, depth, and resolution
* ✅ Proven performance in agricultural image tasks

---

## 📊 Model Evaluation Report

| Metric       | Value      |
| ------------ | ---------- |
| ✅ Accuracy   | **95.69%** |
| 🎯 Precision | 95.98%     |
| 🔁 Recall    | 95.69%     |
| 📉 MSE       | 4.6521     |

### 🧩 Intersection over Union (IoU) - Samples

* Apple Black Rot: **0.9048**
* Tomato Yellow Leaf Curl Virus: **0.9871**
* Corn Healthy: **0.9915**
* Tomato Early Blight: **0.6275**
* Strawberry Leaf Scorch: **0.8346**

> (Full IoU values across 39 classes included in PDF report)

### 📦 Confusion Matrix

A detailed confusion matrix was used to evaluate per-class accuracy and detect misclassifications.

### ℹ️ mAP / SSIM / PSNR Notes

* **mAP**: Estimated via IoU, not explicitly computed
* **SSIM / PSNR**: Not applicable as task is classification, not image reconstruction

---

## ⚙️ Optimization Techniques Used

| Technique                  | Purpose                                       |
| -------------------------- | --------------------------------------------- |
| `tf.data.AUTOTUNE`         | Accelerate data pipeline                      |
| **Transfer Learning**      | Leverage pre-trained EfficientNetB4           |
| **Fine-tuning Layers**     | Improve domain-specific accuracy              |
| **Batch Size = 32**        | Efficient memory usage and training stability |
| **Input Size = 160×160**   | Balances speed and accuracy                   |
| **Dropout Regularization** | Prevents overfitting during fine-tuning       |

---

## 🖼️ Training & Validation Accuracy

> Plot available in the notebook — visualize accuracy/loss over both training stages.

```python
plt.plot(acc, label='Training Accuracy')
plt.plot(val_acc, label='Validation Accuracy')
```

---

## 🧾 Project Summary

* 🧠 **Deep CNN model** built with **EfficientNetB4** for plant disease detection
* 🌱 Based on 39-class PlantVillage dataset
* 🚀 Achieved near 96% accuracy and robust IoU performance
* 🔧 Optimized pipeline: transfer learning, fine-tuning, batch tuning, dropout
* 📱 Ready for real-time, mobile, or embedded deployment

---

## 📂 Resources

* 🌐 [Live Streamlit App](https://hackathonpavaman.streamlit.app/)

---

## 👨‍💻 Team Credits

* **Muthu Munia Rajan**
* **Mohammed Thaher**
* **Murali**
* **Mohamed Farvez**

---

## 🪪 License

Distributed under the **MIT License** — see `LICENSE` for details.

