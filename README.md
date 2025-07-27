# 📰 Multi-News Article Summarizer

A powerful and easy-to-use web app that summarizes multiple news articles into a concise, coherent summary using fine-tuned transformer models. Built with Hugging Face Transformers, PyTorch, and deployed using Streamlit.

🚀 **Live App**: [Click here to try it out!](https://newton-news-summarized.streamlit.app/)

---

## 📌 Features

- 📚 Summarizes multiple news articles into a single, readable summary
- 🧠 Fine-tuned transformer models: `facebook/bart-base` and `t5-small`
- 🧼 Cleaned and tokenized datasets using `multi_news` corpus
- 📊 ROUGE-based evaluation metrics
- 🌐 User-friendly UI powered by Streamlit

---

## 📂 Dataset

This app uses the **[Multi-News Dataset](https://huggingface.co/datasets/multi_news)**:
- ~44,000 training samples
- Each sample includes multiple news documents and a human-written summary
- Preprocessed to split articles using delimiters (`|||||`)

---

## 🛠️ Tech Stack

| Component     | Description                                 |
|---------------|---------------------------------------------|
| `Transformers` | Model training and inference (BART, T5)     |
| `PyTorch`     | Backend training support                     |
| `Streamlit`   | Web app interface                            |
| `Hugging Face Datasets` | Loading and preprocessing datasets |

---

## 🧪 Model Training

### ✅ Preprocessing
- Cleaned HTML/markup and lowercased text
- Split long documents using custom delimiters (`|||||`)
- Tokenized using `facebook/bart-large-cnn` tokenizer

### ⚙️ Fine-Tuning (BART)
- Used a subset of 1000 samples from training & validation sets
- Trained with `Trainer` API from Hugging Face
- Used `fp16`, gradient accumulation, and evaluation after each epoch

### 📈 Evaluation Metrics
- ROUGE-1, ROUGE-2, ROUGE-L (with stemming)
- Example score:  
  ROUGE Scores:
  ROUGE-1: 32.6
  ROUGE-2: 14.7
  ROUGE-L: 28.9
  
---

## 🖥️ Usage

### 🔧 Install dependencies

```bash
pip install -r requirements.txt

▶️ Run the app locally
streamlit run app.py

📤 Input Format
Paste multiple news articles separated by |||||

