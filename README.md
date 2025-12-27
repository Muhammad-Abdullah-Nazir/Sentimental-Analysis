#  Rule-Based Sentiment Analysis on GR / CR Comments

This project implements a **simple rule-based sentiment analysis system** in Python to classify **GR (Good Remarks)** and **CR (Critical Remarks)** comments using a **lexicon-based approach**.

Instead of machine learning, the system relies on **manually defined positive and negative words** to compute sentiment scores and evaluate accuracy.

---

##  Project Objective

* Analyze short textual comments related to **GR / CR feedback**
* Predict sentiment using **rule-based NLP**
* Compare predicted sentiment with true labels
* Evaluate performance using **accuracy and confusion matrix**

---

##  Technologies Used

* **Python 3**
* **Pandas** – Data loading, processing, and evaluation
* **Regular Expressions (re)** – Text cleaning
* **CSV files** – Dataset input & output

---

##  Dataset

* **Input File:** `gr_cr_comments.csv`
* **Key Columns:**

  * `comment` → Textual feedback
  * `label` → Original tag (`gr` or `cr`)

### Label Mapping:

| Original Label | Sentiment |
| -------------- | --------- |
| `gr`           | Positive  |
| `cr`           | Negative  |

---

##  1. Text Preprocessing

Each comment undergoes basic preprocessing:

* Lowercasing
* Normalization of apostrophes
* Removal of punctuation & special characters
* Tokenization using whitespace splitting

 **Function Used:**

```python
tokenize(text)
```

---

##  2. Sentiment Lexicon

### Positive Words

Examples:

```
hard, helpful, kind, supportive, great, excellent, motivates
```

### Negative Words

Examples:

```
lazy, late, angry, boring, worst, forget, problems
```

The sentiment score is calculated as:

```
score = positive_word_count − negative_word_count
```

---

##  3. Rule-Based Sentiment Classification

 **Logic:**

* Score > 0 → Positive
* Score < 0 → Negative
* Score = 0 → Neutral

 **Function Used:**

```python
simple_sentiment(comment)
```

Returns:

* Predicted sentiment
* Numerical sentiment score

---

##  4. Applying Sentiment to Dataset

The system:

* Applies sentiment function to all comments
* Stores results in new columns:

  * `predicted_sentiment`
  * `score`
  * `true_sentiment`

 **Output File Generated:**

```
gr_cr_comments_with_sentiment.csv
```

---

##  5. Model Evaluation

### Accuracy

Neutral predictions are treated as **incorrect**.

```
Accuracy = Correct Predictions / Total Samples
```

### Confusion Matrix

Displays:

* True sentiment vs Predicted sentiment
* Helps analyze misclassifications

---

##  Neutral Case Review

All **neutral predictions** are printed separately to allow:

* Manual review
* Improvement of sentiment lexicon
* Future model refinement

---

##  Project Structure

```
├── Sentiment Analysis.ipynb
├── gr_cr_comments_with_sentiment.csv
├── gr_cr_comments.csv
├── README.md
```

---

##  Use Cases

* Beginner NLP projects
* Rule-based sentiment analysis
* Text analytics without machine learning
* Educational demonstrations
* Feedback analysis systems

---

##  Learning Outcomes

✔ Understand rule-based sentiment analysis
✔ Learn text preprocessing without ML
✔ Work with real CSV datasets
✔ Evaluate predictions using accuracy & confusion matrix

---

##  Author

**Abdullah Nazir**
Python | NLP | Data Analysis

---



Just tell me 👍
