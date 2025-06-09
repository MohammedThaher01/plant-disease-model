# 🌾 Crop Disease Detection using EfficientNetB4

![Model Diagram](https://raw.githubusercontent.com/bmuralisridharan/Hackathon_Pavaman/main/assets/model.png)

> **Accurately detect plant diseases using RGB images and deep learning with 95.6% test accuracy.**
> 🚀 Live Demo: [Streamlit App](https://hackathonpavaman.streamlit.app/)
> 🧠 Model: EfficientNetB4 | 📦 Dataset: [PlantVillage (Mendeley)](https://data.mendeley.com/datasets/tywbtsjrjv/1)

---

## 📌 Project Overview

Crop diseases threaten agricultural productivity worldwide. This project leverages **transfer learning** with **EfficientNetB4** to automatically classify plant leaf diseases using image data.

* ✅ 39 Disease Categories
* 🌱 Based on the **PlantVillage** dataset
* ⚡ Fine-tuned EfficientNetB4
* 📊 Achieved **95.69% accuracy** on the test set
* 💻 Optimized for real-time inference

---

## 📁 Dataset

* **Source**: [PlantVillage (Mendeley)](https://data.mendeley.com/datasets/tywbtsjrjv/1)
* **Augmented dataset**: Included in the ZIP
* **Download**:

  ```bash
  wget -O dataset.zip "https://data.mendeley.com/public-files/datasets/tywbtsjrjv/files/b4e3a32f-c0bd-4060-81e9-6144231f2520/file_downloaded"
  unzip dataset.zip
  ```

---

## 🛠️ Model Architecture

| Component            | Detail                            |
| -------------------- | --------------------------------- |
| 📦 Base Model        | EfficientNetB4 (ImageNet weights) |
| 🧠 Training Strategy | Transfer Learning + Fine Tuning   |
| 🎯 Input Size        | 160 × 160 × 3                     |
| 🔁 Optimizer         | Adam                              |
| 📉 Loss Function     | SparseCategoricalCrossentropy     |
| 📊 Metrics           | SparseCategoricalAccuracy         |

### ⚙️ Transfer Learning Flow

1. Freeze base EfficientNetB4
2. Add Global Avg Pooling + Dropout + Dense
3. Train for 6 epochs
4. Unfreeze top layers and fine-tune from layer 100
5. Continue training for 10 more epochs

---

## 📈 Performance

| Metric       | Value      |
| ------------ | ---------- |
| ✅ Accuracy   | **95.69%** |
| 🎯 Precision | 95.98%     |
| 🔁 Recall    | 95.69%     |
| 📉 MSE       | 4.6521     |

> Also evaluated using **IoU** for each class.
> See full report in `plant_disease_model_documentation.pdf`.

---

## 🧪 Evaluation Visuals

![Predictions](https://raw.githubusercontent.com/bmuralisridharan/Hackathon_Pavaman/main/assets/predictions.png)

---

## 🚀 Deployment

* ✅ **Streamlit App**: [https://hackathonpavaman.streamlit.app](https://hackathonpavaman.streamlit.app)
* 📂 **Model Export**:

  ```python
  model.save("plant_disease_recog_model_pwp.keras")
  ```

---

## 🧠 Why EfficientNetB4?

* ⚖️ Best trade-off between speed and accuracy
* 📱 Optimized for mobile & low-resource deployment
* ⏱️ Faster convergence using ImageNet pre-trained weights
* 🌍 Robust across lighting, angle, and crop types

---

## 🧬 Optimization Techniques

* **📦 tf.data AUTOTUNE**: Pipelined input for faster training
* **📐 Batch Size**: 32 — balanced for convergence and memory
* **🖼️ Input Size**: 160×160 — optimized for speed
* **🔧 Compound scaling** in EfficientNet for resource efficiency

---

## 💻 Run It Yourself

```bash
pip install tensorflow matplotlib split-folders
# Download and unzip dataset
# Then run the training notebook (Colab link available)
```

---

## 📂 Repository & Resources

* 🔗 [GitHub Repo](https://github.com/bmuralisridharan/Hackathon_Pavaman)
* 📄 [Documentation PDF](plant_disease_model_documentation.pdf)

---

## 👥 Team Credits

* 🧑‍💻 Mohammed Thaher S.
* 👨‍💻 \[Your teammates’ names here]

---

## 🏁 Final Words

This project showcases the power of transfer learning in solving real-world agricultural challenges. With high accuracy and real-time performance, it has potential applications in **mobile crop advisory**, **agri-health monitoring**, and **smart farming**.
