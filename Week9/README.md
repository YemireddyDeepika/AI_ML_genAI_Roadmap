# Week 9 — RNN & NLP Pipeline

This project implements a **Complete NLP Pipeline** using:

-   **LSTM** for Sentiment Analysis (Positive/Negative classification)\
-   **Bidirectional LSTM** for Named Entity Recognition (BIO tagging)\
-   **PyTorch, NLTK, and Gradio** for model building and UI\
-   **Custom tokenizer and FAISS vocab** for text processing

The pipeline takes any input sentence and returns the **sentiment with
confidence score** and **all named entities detected**.

------------------------------------------------------------------------

## Features

-   Text preprocessing (cleaning, tokenization, stopword removal)\
-   Sentiment Analysis — Positive/Negative + confidence %\
-   Named Entity Recognition — PERSON, ORGANIZATION, LOCATION\
-   BIO tagging format (B-PER, I-PER, B-ORG, B-LOC, I-LOC)\
-   Bidirectional LSTM for better context understanding\
-   Combined pipeline on any input sentence\
-   Gradio web UI with public shareable link

------------------------------------------------------------------------

## Project Structure

    Week9_NLP/
    │
    ├── RAG_Document_QA.ipynb       ← Main Colab notebook (8 cells)
    ├── sentiment_analysis.py       ← Standalone sentiment model
    ├── ner_model.py                ← Standalone NER model
    ├── nlp_pipeline.py             ← Combined pipeline
    └── README.md

------------------------------------------------------------------------

## Daily Breakdown

  Day     Topic                       Key Concept Learned
  ------- --------------------------- -----------------------------------------
  Day 1   RNN Basics                  Hidden state, output vs hidden shapes
  Day 2   LSTM & GRU                  Cell state, vanishing gradients, 3 gates
  Day 3   Text Preprocessing          Cleaning, stemming, word2idx, padding
  Day 4   Seq2Seq Models              Encoder-Decoder, context vector problem
  Day 5   Sentiment Analysis          BCELoss, Sigmoid, Dropout, confidence
  Day 6   Named Entity Recognition    BIO tagging, Bidirectional LSTM
  Day 7   Capstone — NLP Pipeline     Combined Sentiment + NER pipeline

------------------------------------------------------------------------

## Methodology

### 1. Text Preprocessing

-   Lowercase and remove punctuation\
-   Tokenize into individual words\
-   Remove stopwords (the, is, a, and...)\
-   Build vocabulary and word2idx mapping\
-   Pad sequences to equal length for batch training

### 2. Sentiment Analysis (LSTM)

-   Train LSTM model: Embedding → LSTM → Dropout → Sigmoid\
-   BCELoss for binary classification (Positive=1, Negative=0)\
-   Output single probability → confidence score (0–100%)

### 3. Named Entity Recognition (Bidirectional LSTM)

-   Bidirectional LSTM reads left→right AND right→left\
-   BIO tagging marks entity boundaries clearly\
-   CrossEntropyLoss across 7 tag classes\
-   Identifies PERSON, ORGANIZATION, LOCATION entities

### 4. Combined Pipeline

-   Run Sentiment model → get Positive/Negative + confidence\
-   Run NER model → get entity tags per word\
-   Display both results together in clean format

------------------------------------------------------------------------

## Model Architecture

### Sentiment LSTM

    Embedding(vocab_size, 16)
          ↓
    LSTM(16, 32, batch_first=True)
          ↓
    Dropout(0.3)
          ↓
    Linear(32, 1)
          ↓
    Sigmoid → probability (0 to 1)

### NER Bidirectional LSTM

    Embedding(vocab_size, 32)
          ↓
    BiLSTM(32, 64, bidirectional=True)
          ↓
    Dropout(0.3)
          ↓
    Linear(128, 7)    ← 128 = 64×2 for bidirectional
          ↓
    argmax → tag prediction per word

------------------------------------------------------------------------

## Sample Output

```
==================================================
Input: Deepika loves working at Google in Hyderabad
==================================================

SENTIMENT ANALYSIS
   Sentiment  : Positive 😊
   Confidence : 94.5%

NAMED ENTITY RECOGNITION
   Word            Entity Tag
   ------------------------------
   Deepika         B-PER
   loves           O
   working         O
   at              O
   Google          B-ORG
   in              O
   Hyderabad       B-LOC

Entities Found: [('Deepika','B-PER'),('Google','B-ORG'),('Hyderabad','B-LOC')]
==================================================
```

------------------------------------------------------------------------

## Installation

### Clone Repository

``` bash
git clone https://github.com/YemireddyDeepika/week9-rnn-nlp.git
cd week9-rnn-nlp
```

### Install Dependencies

``` bash
pip install torch transformers sentence-transformers nltk gradio numpy faiss-cpu
```

------------------------------------------------------------------------

## Run the Project

### Google Colab (Recommended)

``` python
# Run all 8 cells in order (1 → 8)
# Cell 8 launches Gradio UI automatically
demo.launch(share=True)
```

### VS Code / Terminal

``` bash
python nlp_pipeline.py
```

------------------------------------------------------------------------

## Result

  Metric               Value
  -------------------- ----------------------------------------
  Sentiment Model      LSTM (BCELoss + Sigmoid)
  NER Model            Bidirectional LSTM (BIO tagging)
  Entities Detected    PERSON, ORGANIZATION, LOCATION
  Tags                 O, B-PER, I-PER, B-ORG, I-ORG, B-LOC, I-LOC
  Training Epochs      100
  UI                   Gradio (public URL)
  Accuracy             ~90%+ on training sentences

------------------------------------------------------------------------

## Key Concepts Learned

  Concept                  Description
  ------------------------ --------------------------------------------------
  RNN                      Sequential model with hidden state memory
  LSTM                     Adds cell state to solve vanishing gradient
  GRU                      Simplified LSTM with 2 gates, faster training
  BIO Tagging              B=Beginning, I=Inside, O=Outside entity
  Bidirectional LSTM       Reads sentence both left→right and right→left
  BCELoss                  Binary Cross Entropy for 2-class classification
  CrossEntropyLoss         Multi-class loss for 7 NER tags
  Dropout                  Randomly disables neurons to prevent overfitting
  OOV Problem              Out-of-Vocabulary words get wrong tags → fix by adding to training data
  Vanishing Gradient       RNN forgets early words → fixed by LSTM cell state

------------------------------------------------------------------------

## Bugs Fixed During Development

-   `torch.no_grad()` missing `torch.` prefix → fixed\
-   `prod` vs `prob` variable name typo → fixed\
-   Double sigmoid application removed\
-   Indentation errors in `answer_question()` function → fixed\
-   Comment block accidentally redefining function with 0 parameters → fixed\
-   Confidence showing `0.36` instead of `36.0%` → multiply by 100\
-   `<s>` special token returned as answer → caught and handled

------------------------------------------------------------------------

## Learning Outcomes

-   Understanding **RNN, LSTM, GRU** and when to use each\
-   Solving **vanishing gradient** with LSTM cell state\
-   Implementing **BIO tagging** for entity boundaries\
-   Using **Bidirectional LSTM** for richer context\
-   Debugging **OOV (Out of Vocabulary)** by extending training data\
-   Combining multiple models into one **end-to-end NLP pipeline**

------------------------------------------------------------------------

## Future Improvements

-   Fine-tune on CoNLL-2003 dataset for production NER accuracy\
-   Add neutral sentiment class (3-way: Positive/Neutral/Negative)\
-   Integrate with Week 8 RAG pipeline for document-level NLP\
-   Deploy as full web application with FastAPI backend

------------------------------------------------------------------------

## Author

**Deepika Yemireddy**\
B.Tech — Computer Science\
Hyderabad, India

Email: **deepika.cvg1@gmail.com**\
GitHub: **github.com/YemireddyDeepika**\
LinkedIn: **linkedin.com/in/yemireddy-deepika**
