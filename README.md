# Image Captioning using EfficientNetB3, GloVe Embeddings, and Beam Search

This project generates natural language captions for images using a **CNN + LSTM-based deep learning model**.  
It combines **computer vision** and **natural language processing (NLP)The model was progressively upgraded from an initial baseline to a more advanced and semantically powerful architecture.

This final version uses:

EfficientNetB3 for visual feature extraction

GloVe 100D pretrained embeddings for richer semantic understanding

Beam Search decoding for more fluent captions

---

##  Project Evolution (Upgrades Made)
1. EfficientNetB0 → EfficientNetB3

The original encoder used EfficientNetB0 (1280-dim features).
This was upgraded to EfficientNetB3 (1536-dim features), providing:

higher-quality feature representations

better generalization on diverse scenes

improved caption detail and accuracy

2. Random Embeddings → GloVe Pretrained Embeddings

Earlier, embeddings were randomly initialized and learned from scratch.
The new version uses GloVe 100D pretrained word embeddings, giving:

better semantics (related words are close)

more natural sentence structure

more diverse and meaningful vocabulary usage

3. Beam Search Decoding

Greedy decoding selects the highest-probability word at each step but often produces short or generic captions.
Beam Search evaluates multiple caption paths and chooses the best one.

This results in:

more complete captions

fewer repetitive phrases

more accurate descriptions

Example
Input Image	Predicted Caption
🧍‍♀️👕	"a woman in a blue and white shirt is jogging on a road"

---

## Model Architecture
1. CNN Encoder – EfficientNetB3

Pretrained on ImageNet

Outputs a 1536-dimensional feature vector

Extracts high-level semantic information from images

2. Text Embedding – GloVe 100D

Pretrained word vectors

Fine-tuned on Flickr8k captions

Maps words into a meaningful semantic space

3. Caption Decoder – LSTM

LSTM size: 512 units

Time-Distributed Dense softmax layer

Teacher forcing during training

Max sequence length: 20 tokens

---

## Dataset

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
pip install -r requirements.txt