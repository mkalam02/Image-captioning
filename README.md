# Image Captioning using CNN + LSTM

This project generates natural language captions for images using a **CNN + LSTM-based deep learning model**.  
It combines **computer vision** and **natural language processing (NLP)** to describe what is happening in an image.

---

##  Project Overview

The model extracts **visual features** from an image using **EfficientNetB0 (CNN)**,  
then passes these features into a **sequence decoder (LSTM)** that generates a descriptive caption word by word.

Example:

| Input Image | Predicted Caption |
|--------------|------------------|
| 🧍‍♀️👕 | *"a woman in a blue and white shirt is jogging on a road"* |

---

## 🧠 Model Architecture

1. **Feature Extractor (CNN)**  
   - Pretrained **EfficientNetB0** is used to encode image features (1280-dimensional).  
   - These features represent the high-level visual content.

2. **Caption Decoder (LSTM)**  
   - A sequential model with:
     - Embedding layer  
     - LSTM layers  
     - Dense + Softmax for word prediction  
   - Trained to predict the next word in a caption given the previous words and image context.

---

## 📊 Dataset

- **Dataset:** [Flickr8k](https://www.kaggle.com/datasets/adityajn105/flickr8k)
- **Images:** 8,000 photos
- **Captions:** 5 captions per image (≈ 40,000 total)

Each caption describes the content of the corresponding image in natural English.

---

## 🧰 Technologies Used

| Category | Tools |
|-----------|-------|
| Language | Python |
| Libraries | TensorFlow / Keras, NumPy, Pandas, Matplotlib |
| Pretrained Model | EfficientNetB0 |
| Environment | Jupyter Notebook |
| Dataset Source | Kaggle (Flickr8k) |

---

## 🚀 How to Run

### 1️⃣ Clone this repository
```bash
git clone https://github.com/mkalam02/image-captioning.git
cd image-captioning
