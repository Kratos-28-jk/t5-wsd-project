# Contextual Word Sense Disambiguation using T5

## 📌 Project Overview

This project implements a **Word Sense Disambiguation (WSD)** system using the **T5 Transformer model**. The goal is to determine whether a given word has the **same meaning across two different sentences**, based on contextual understanding.

The project follows a complete machine learning pipeline:

* Data loading & preprocessing
* Model training (T5 fine-tuning)
* Evaluation
* Deployment via a simple application

---

## 📂 Project Structure

```
├── models/                     # Saved trained models
├── step1_load_and_clean.py    # Data loading & preprocessing
├── step2_train_model.py       # Model training script
├── step3_evaluate.py          # Evaluation metrics & results
├── step4_app.py               # Application / inference script
├── requirements.txt           # Dependencies
├── evaluation_report.png      # Model performance visualization
└── README.md                  # Project documentation
```

---

## 📊 Dataset Description

The project uses the **WiC (Word-in-Context)** dataset, part of the SuperGLUE benchmark.

Each sample consists of:

* A **target word**
* Two **sentences containing the same word**
* A **label** indicating meaning similarity

### Labels:

* `1` → Same meaning (Yes)
* `0` → Different meaning (No)

👉 As described in your report , the dataset includes **training, validation, and test splits**, and covers both **noun and verb usages**, making it suitable for contextual semantic understanding.

---

## ⚙️ Methodology

### 1. Data Preprocessing

* Load dataset using Hugging Face `datasets`
* Convert data into T5 text-to-text format:

  ```
  Sentence 1: ...
  Sentence 2: ...
  Word: ...
  ```
* Output labels:

  ```
  Yes / No
  ```

### 2. Model Training

* Fine-tuned **T5 Transformer**
* Tokenization using T5 tokenizer
* Training using PyTorch

### 3. Evaluation

* Accuracy-based evaluation on validation & test sets
* Error analysis for ambiguous cases

---

## 🧠 Model Details

* Architecture: **Encoder-Decoder Transformer (T5)**
* Training Framework: PyTorch + Hugging Face Transformers
* Optimization:

  * Learning Rate: ~9.76e-5
  * Batch Size: 16
  * Dropout: 0.45

👉 These hyperparameters are reported in your project results .

---

## 📈 Results

* Strong training & validation performance
* Moderate generalization on test data
* Effective in capturing contextual meaning

Example insight:

* Works well for common words
* Struggles with highly ambiguous or rare contexts

---

## 🚀 How to Run

### 1. Install Dependencies

```bash
pip install -r requirements.txt
```

### 2. Run Pipeline

#### Step 1: Data Preprocessing

```bash
python step1_load_and_clean.py
```

#### Step 2: Train Model

```bash
python step2_train_model.py
```

#### Step 3: Evaluate Model

```bash
python step3_evaluate.py
```

#### Step 4: Run Application

```bash
python step4_app.py
```

---

## 📌 Expected Output

* Trained T5 model saved in `/models`
* Evaluation metrics
* Prediction system for:

  ```
  Input: Two sentences + word
  Output: Yes / No
  ```

---

## 🔍 Future Improvements

* Data augmentation (paraphrasing)
* Larger transformer models (T5-large, FLAN-T5)
* Domain-specific fine-tuning
* Improved handling of rare word senses

---

## 📚 References

1. WiC Dataset – SuperGLUE Benchmark
2. Raffel et al. – T5 Model
3. Transformer Architecture Research Papers

---

## 👨‍💻 Authors

* Jaya Krishna B
* Dinesh Kumar P
* Arpit Saxena

---

## 🏁 Conclusion

This project demonstrates how transformer models like T5 can effectively solve **contextual ambiguity problems in NLP**, providing a strong foundation for advanced semantic understanding systems.

---
