# 📝 Text Summarization API

A lightweight Flask-based API that performs automatic text summarization using Natural Language Processing (NLP). It leverages **NLTK** to tokenize, filter, and analyze the frequency of words, extracting the most meaningful sentences from the input. The API also returns a basic "accuracy" metric based on word overlap.

---

## 🚀 Features

- 🔍 **Summarization**: Extracts the top 5 sentences that best summarize the given input text.
- 📊 **Accuracy Calculation**: Computes a basic score based on how many key words from the original text are retained in the summary.
- 🌐 **CORS Enabled**: Easily integrate with frontend frameworks or external applications.
- ⚙️ **Simple REST API**: Designed for quick use and easy deployment.

---

## 🛠️ Tech Stack

| Layer         | Technology       |
|---------------|------------------|
| Language      | Python 3.7+       |
| Framework     | Flask            |
| NLP Toolkit   | NLTK             |
| API Utility   | Flask-CORS       |

---

## 📂 API Endpoints

### ✅ `GET /`
Health check route  
**Response:**  
```text
Hello, World!
```

---

### ✨ `POST /get_summary`

Generates a summary and computes accuracy based on the shared word ratio.

**Request Body:**

```json
{
  "text": "Paste your text here..."
}
```

**Response:**

```json
{
  "summary": "Generated summary text...",
  "accuracy": 0.42
}
```

---

## ⚙️ How It Works

1. **Sentence Tokenization**: Splits the paragraph into individual sentences.
2. **Word Tokenization + Cleaning**: Removes punctuation, converts to lowercase, and removes stopwords.
3. **Frequency Distribution**: Calculates how often each word appears.
4. **Sentence Scoring**: Scores each sentence based on the sum of the word frequencies.
5. **Summary Generation**: Picks the top 5 highest-scoring sentences.
6. **Accuracy Calculation**: Compares word overlap between summary and original text.

---

## 🧪 Example Usage

### Input:
```text
Text summarization is the process of distilling the most important information from a source text. It helps users grasp the key concepts without reading the entire content. There are different types of summarization such as extractive and abstractive...
```

### Output:
```json
{
  "summary": "Text summarization is the process of distilling the most important information from a source text. It helps users grasp the key concepts...",
  "accuracy": 0.57
}
```

---

## 📦 Installation Guide

### 🔧 Clone and Setup

```bash
git clone https://github.com/your-username/text-summary-api.git
cd text-summary-api
```

### 🧪 Create Virtual Environment (Optional)

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 📥 Install Dependencies

```bash
pip install flask flask-cors nltk
```

### 📚 Download NLTK Data

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```

### ▶️ Run the App

```bash
python app.py
```

Visit: [http://localhost:5000](http://localhost:5000)

---

## 📁 Project Structure

```
.
├── app.py              # Main Flask application
├── README.md           # Documentation
├── requirements.txt    # List of Python dependencies (optional)
```

---
