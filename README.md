# phishing-detection-albert  
Detecting phishing emails using ALBERT embeddings combined with deep neural network architectures.

# 🧠 Phishing Detection with ALBERT: Embedding-Powered Deep Learning

## 📌 Project Overview  
This project applies ALBERT (`albert-base-v2`) for phishing email classification. ALBERT embeddings are extracted and fed into a series of deep learning classifiers — including RNN-LSTM and stacked LSTM networks — to detect phishing intent in emails. Extensive preprocessing, batch-wise embedding generation, and model evaluation with accuracy/loss plots and confusion matrices are included.

---

## 📂 Dataset & Source

- **Input Datasets**: _(you may insert your own links)_
  - `set1`: Traditional labeled email dataset  
  - `set2`: Evaluation/testing email dataset  
  - `set3`: Public email phishing challenge data  
- **Format**:
  ```csv
  Text,label
  "Confirm your credentials now",1
  "Here's your payment receipt",0

🔍 Insights & Findings
✂️ Texts were cleaned using regex, stripped of digits and punctuations.

🔤 ALBERT tokenizer was used with max length 128 and padded sequences.

📊 Best-performing models leveraged stacked LSTM and RNN-LSTM over ALBERT embeddings.

🧠 Embeddings were extracted using the [CLS] token and processed in batches via TensorFlow.

Model	Accuracy (Est.)
ANN	~94%
CNN	~95%
RNN-LSTM	~97%
Stacked LSTM	~98%

🤖 AI Pipeline Summary
Stage	Description
Preprocessing	Lowercasing, punctuation & digit removal (regex)
Embedding Extraction	ALBERT [CLS] token, batched with attention mask
Classifier Input	768-dim vectors per text
Model Evaluation	Accuracy, F1-score, confusion matrix, metric plots

📈 Visualizations (Notebook Output)
✅ Training vs Validation Loss plot

✅ Training vs Validation Accuracy plot

✅ Confusion Matrix for each model

✅ All visualizations generated per model via matplotlib

🛠️ Models Implemented
ANN — Dense layers with dropout, sigmoid output

CNN — 1D convolution layers with flattening

RNN-LSTM — SimpleRNN → LSTM with dropout

ANN-LSTM — Dense layers reshaped and fed to LSTM

CNN-LSTM — Conv1D followed by dual-layer LSTM

Stacked LSTM — Three stacked LSTM layers (128 → 64 → 32)

All models trained with:
• binary_crossentropy loss
• Adam optimizer
• Batch size: 64
• Early stopping (patience = 3)
