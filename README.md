# Bridging Communication Gaps: Sign Language Interpretation with Deep Learning

This project develops a highly accurate **Convolutional Neural Network (CNN)** capable of classifying all **29 classes** of the American Sign Language (ASL) alphabet, and applies this model to decode a complete sentence from a simulated video sequence.

The core achievement lies in successful **hyperparameter tuning**, **robust training**, and the creation of a custom **sequential video-decoding pipeline** that bridges the gap between static image classification and temporal interpretation.

---

# Key Features

- **High-Accuracy CNN Classifier**  
  Achieved **99.88% validation accuracy** and **100.00% test accuracy** on the ASL Alphabet dataset.

- **Hyperparameter Optimization**  
  Used **KerasTuner (Hyperband)** to find the best architecture and training configuration, leading to outstanding generalization.

- **Sequential Decoding Pipeline**  
  Converts frame-by-frame predictions into clean text using:  
  - **Majority voting**  
  - **Pixel-based space detection**  
  - **Repetition collapsing**

- **Robust Training Process**  
  Integrated **EarlyStopping** and **ModelCheckpoint** to automatically store the best-performing model.

---

# Project Methodology

### 1. Data Preparation
- Loaded the ASL Alphabet Dataset (~87,000 images, 29 classes).  
- Resized images to **128×128** and split into **80% training / 20% validation**.

### 2. Baseline Model
- Built a 3-block Sequential CNN (filters: 32 → 64 → 128).  
- Included **Dropout(0.5)** and **Adam(0.001)**.

### 3. Hyperparameter Tuning
- Used **KerasTuner + Hyperband** to optimize:  
  - Number of convolutional blocks  
  - Filter sizes  
  - Dropout rate  
  - Dense layer size  
  - Learning rate  

### 4. Final Training
- Applied **EarlyStopping** to prevent overfitting and **restore best weights**.  
- Achieved peak validation accuracy of **98.63%**.

### 5. Video Decoding
- Simulated a video by selecting one random image per frame for each letter.  
- Applied a **smart decoding filter** to produce the final sentence output.



