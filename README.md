#  Word2Vec on IIT Jodhpur Corpus

##  Overview

This project focuses on learning word embeddings using the Word2Vec model on a domain-specific corpus created from IIT Jodhpur data. The workflow includes dataset preparation, preprocessing, manual implementation of Word2Vec (CBOW and Skip-gram), and evaluation using similarity, analogies, and visualization techniques.

---

## Objectives

* Build a clean textual corpus from IIT Jodhpur sources
* Perform preprocessing and corpus optimization
* Train Word2Vec models (CBOW & Skip-gram with Negative Sampling)
* Analyze embeddings using similarity and analogies
* Visualize embeddings using PCA and t-SNE

---

##  Project Structure

```
├── NLU_Prob1.ipynb        # Dataset preparation and preprocessing
├── NLU_Prob2.ipynb        # Word2Vec training (CBOW & Skip-gram)
├── raw_corpus.txt         # Extracted raw text
├── final_corpus.txt       # Cleaned and optimized corpus
├── clean_corpus.txt       # Tokenized corpus
├── cbow_pca.png           # PCA visualization (CBOW)
├── cbow_tsne.png          # t-SNE visualization (CBOW)
├── skipgram_pca.png       # PCA visualization (Skip-gram)
├── skipgram_tsne.png      # t-SNE visualization (Skip-gram)
└── README.md              # Project documentation
```

---

##  Dataset Preparation

* Data collected from IIT Jodhpur websites and academic PDFs
* HTML and PDF text extraction performed
* Combined into a single raw corpus

---

##  Preprocessing Steps

1. Removal of boilerplate content (headers, footers, scripts)
2. Cleaning (removal of special characters, lowercasing)
3. Tokenization using NLTK
4. Stopword removal
5. Filtering rare and frequent words
6. Vocabulary and token size control (~25,000 tokens)
7. Domain-specific augmentation (UG, PG, PhD relationships)

---

##  Model Training

Two Word2Vec models were implemented manually using NumPy:

###  CBOW

* Predicts target word from context
* Faster but less expressive

###  Skip-gram

* Predicts context from target word
* Better for semantic relationships

###  Hyperparameters

* Embedding dimensions: 50, 100, 200, 300
* Window size: 3, 5
* Negative samples: 5, 10
* Learning rate: 0.01

---

##  Evaluation

###  Top Words (Frequency-based)

Common words include:
`program, student, course, research, academic, phd, masters`

---

###  Example Embedding

```
student - 0.1284, -0.0921, 0.4410, ..., 0.0037
```

---

###  Analogies

* UG : BTech :: PG : Masters
* Student : Exam :: Researcher : Publication
* BTech : Course :: PhD : Research

---

##  Visualization

Word embeddings were visualized using:

* **PCA (Principal Component Analysis)**
* **t-SNE (t-distributed Stochastic Neighbor Embedding)**

Skip-gram showed better clustering compared to CBOW.

---

##  Key Observations

* Skip-gram captures semantic relationships better
* Larger embedding dimensions improve representation quality
* Domain-specific augmentation improves analogy performance
* t-SNE provides clearer cluster separation than PCA

---

##  Limitations

* Limited dataset size affects embedding quality
* Manual implementation is slower than optimized libraries
* Some analogies may not be perfectly captured

---

##  How to Run

1. Install dependencies:

```
pip install numpy nltk matplotlib scikit-learn
```

2. Run notebooks:

* First run `NLU_Prob1.ipynb` (dataset preparation)
* Then run `NLU_Prob2.ipynb` (model training & evaluation)

---

##  Conclusion

This project demonstrates how word embeddings can be learned from a domain-specific corpus and used to capture semantic relationships. Despite limitations, the models successfully encode meaningful academic relationships.

---

##  Author

Akash Kashyap
M25CSE003
IIT Jodhpur

---
