# 🤖 AI & Machine Learning Hands-on Projects: NLP with SMS Spam Detection

Welcome to my **AI/ML learning journey**, where I explore hands-on projects with a strong focus on **Natural Language Processing (NLP)**. This project demonstrates various **text preprocessing techniques, exploratory data analysis**, and simple spam prediction heuristics using a real-world SMS dataset.

---

## 📌 Project Summary

This project uses the **SMS Spam Collection Dataset** to practice key NLP concepts:
- Text cleaning and normalization
- Tokenization, stemming, lemmatization
- Feature engineering
- Visualization with WordCloud
- Heuristic-based spam prediction
- PII (Personally Identifiable Information) redaction with spaCy

---

## 📁 Dataset

- Source: [`justmarkham/pycon-2016-tutorial`](https://github.com/justmarkham/pycon-2016-tutorial)
- Format: Tab-separated values with two columns: `label` and `text`
- Labels: `ham` (not spam), `spam` (advertisements, phishing, etc.)

---

## 🛠️ Tools & Libraries

- Python
- Pandas
- NLTK
- spaCy
- scikit-learn
- Matplotlib
- WordCloud

---

## 🔎 Text Preprocessing Steps

1. **Text Cleaning**:  
   - Lowercasing  
   - Removing special characters and digits  

2. **Tokenization & Stopword Removal**:  
   Using `word_tokenize()` and NLTK’s English stopword list

3. **Stemming & Lemmatization**:  
   - `PorterStemmer` for stemming  
   - `WordNetLemmatizer` with verb POS for context-aware lemmatization

4. **Feature Engineering**:
   - Character and word counts  
   - Count of digits  
   - Presence of URLs  
   - Count of uppercase words  

---

## 📊 Exploratory Analysis

- WordCloud generated from spam messages reveals common marketing words
- Heuristic-based spam detection using:
  - Messages with more than 5 digits
  - Presence of URLs
  - More than 3 uppercase words

```python
df['predicted_spam'] = (
    (df['num_digits'] > 5) |
    (df['has_url']) |
    (df['uppercase_words'] > 3)
)
