# 🚀 Week 6 – Convolutional Neural Networks & Computer Vision (Days 38–44)

Week 6 focuses on **image understanding using Deep Learning**.
In this week, I learned **Convolutional Neural Networks (CNNs)** and built a
**face recognition–style image classification project**, moving from
basic ANN knowledge to **real computer vision capability**.

---

# 🧠 Topics Covered

## 🔹 Day 38 – Introduction to CNN

* CNN is designed specifically for **image data**.
* Automatically learns:

  * Edges
  * Shapes
  * Patterns
* Performs better than ANN for images because it **preserves spatial structure**.

📌 Outcome: Understanding **why CNNs are essential for computer vision**.

---

## 🔹 Day 39 – Convolution & Pooling

### Convolution Layer

* Uses **filters/kernels** to extract visual features.
* Produces **feature maps** highlighting important patterns.

### Pooling Layer

* Reduces image size while keeping key information.
* Types:

  * **Max Pooling** (most common)
  * Average Pooling

📌 Outcome: Learned **how CNN reduces computation and extracts features**.

---

## 🔹 Day 40 – Image Augmentation

* Technique to **artificially increase dataset size**.
* Methods:

  * Rotation
  * Flipping
  * Zoom
  * Shifting
  * Brightness adjustment

📌 Benefits:

* Prevents **overfitting**
* Improves **model generalization**

---

# 🧪 Days 41–44 – CNN Project: Image / Face Classification

## 🎯 Project Goal

Build a **CNN-based image classification system** capable of
recognizing **faces or object categories** from images.

---

## ⚙️ Steps Performed

### 1️⃣ Data Preparation

* Loaded image dataset
* Resized images to fixed dimensions
* Normalized pixel values (0–255 → 0–1)
* Split into **train / validation / test**

---

### 2️⃣ CNN Architecture

Typical structure used:

* **Convolution → ReLU → Pooling** (repeated blocks)
* **Flatten layer**
* **Dense fully connected layer**
* **Softmax output layer**

This allows the network to learn:

* Low-level features → edges
* Mid-level features → shapes
* High-level features → faces/objects

---

### 3️⃣ Training Setup

* **Loss:** Categorical cross-entropy
* **Optimizer:** Adam
* **Metric:** Accuracy
* Applied **image augmentation** for better performance.

---

### 4️⃣ Evaluation & Prediction

* Measured **test accuracy**
* Visualized **predicted vs actual images**
* Confirmed CNN learns **meaningful visual patterns**.

📈 CNN achieved **significantly higher accuracy than ANN on images**.

---

# 🛠️ Technologies Used

* Python
* NumPy
* Matplotlib
* TensorFlow / Keras
* OpenCV (for image handling)
* Jupyter Notebook
* Git & GitHub

---

# 📂 Suggested Folder Structure

```
Week6_CNN_Computer_Vision/
│
├── Day38_CNN_Intro/
├── Day39_Convolution_Pooling/
├── Day40_Image_Augmentation/
├── Day41_44_CNN_Image_Project/
│
└── README.md
```

---

# 🏆 Week 6 Outcome

After completing Week 6, I can:

* Explain **CNN architecture and working principles**
* Perform **image preprocessing & augmentation**
* Build and train a **CNN model for image classification**
* Evaluate visual deep learning models correctly
* Deliver a **computer vision project for portfolio**

➡ This week marks my transition from
**basic deep learning → practical computer vision engineer**.

---

# 🔜 Next Step

**Week 7 – NLP, RNN, LSTM & Sequence Models**

Upcoming learning:

* Text preprocessing
* Word embeddings
* Recurrent Neural Networks (RNN)
* LSTM/GRU for long-term memory
* **Sentiment Analysis NLP project**

🚀 Moving closer to **Transformers & Generative AI**.
