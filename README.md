
##  Overview

This project implements a comprehensive pipeline for multilingual NLP, exploring various word embedding techniques and cross-lingual alignment methods. Using the **Tatoeba parallel corpus** (English-French), the notebook demonstrates state-of-the-art approaches to representing words as vectors and aligning embeddings across languages.

###  Key Highlights

- **Multiple Embedding Techniques**: One-Hot, TF-IDF, Word2Vec, GloVe, FastText
- **Cross-Lingual Alignment**: MUSE-based bilingual dictionary alignment
- **Complete Pipeline**: From raw parallel data to aligned multilingual embeddings
- **Semantic Analysis**: Synonyms, antonyms, polysemy, and rare word handling
- **Downstream Task**: Language identification classifier
- **One-Click Execution**: Simply run all cells in Google Colab

##  Quick Start

### Prerequisites
- Google Colab account (free tier is sufficient)
- No local installation required!

### Running the Project

1. **Upload the notebook** to Google Colab or click "Open in Colab" button
2. **Run all cells** (Runtime → Run all) or press `Ctrl+F9`
3. **Wait for completion** - All dependencies, datasets, and models are handled automatically
4. **Review results** - Explore visualizations and embedding quality metrics

That's it! The entire pipeline runs end-to-end without any manual intervention.

##  Embedding Methods Implemented

### 1. **One-Hot Encoding**
- Basic discrete representation
- Binary vectors with vocabulary size dimensions
- Baseline for comparison

### 2. **TF-IDF (Term Frequency-Inverse Document Frequency)**
- Statistical weighting approach
- Captures word importance in documents
- Efficient and interpretable

### 3. **Word2Vec**
- Neural word embeddings (Skip-gram/CBOW)
- Captures semantic relationships
- Dense 100-dimensional vectors

### 4. **GloVe (Global Vectors)**
- Matrix factorization approach
- Leverages global co-occurrence statistics
- Custom implementation from scratch

### 5. **FastText**
- Character n-gram based embeddings
- Handles out-of-vocabulary (OOV) words
- Robust for morphologically rich languages

##  Pipeline Architecture

```
Tatoeba Parallel Corpus
  (English ↔ French)
     ↓
Data Preprocessing
  • Tokenization
  • Lowercasing
  • Text cleaning
  • Alignment verification
     ↓
Feature Engineering
  • One-Hot Encoding
  • TF-IDF Vectors
  • Word2Vec Training
  • GloVe Training
  • FastText Training
     ↓
Cross-Lingual Alignment
  • MUSE Bilingual Dictionary
  • Orthogonal Procrustes
  • Rotation Matrix Learning
     ↓
Semantic Analysis
  • Synonym Detection
  • Antonym Analysis
  • Polysemy Exploration
  • OOV Handling
     ↓
PCA Visualization
  • 2D Embedding Space
  • Alignment Quality
     ↓
Downstream Application
  • Language Identification
  • Logistic Regression Classifier
```

##  Dataset

**Tatoeba Parallel Corpus**
- Source: [tatoeba.org](https://tatoeba.org)
- 500+ aligned English-French sentence pairs
- Automatically downloaded and preprocessed
- Real-world translation examples

The preprocessing pipeline handles:
- Automatic download and extraction
- Sentence alignment verification
- Text normalization and cleaning
- Vocabulary building for both languages

##  Cross-Lingual Alignment

### MUSE Dictionary Approach
The project implements **Facebook's MUSE** (Multilingual Unsupervised and Supervised Embeddings) methodology:

1. **Bilingual Dictionary Loading**: Downloads EN-FR word pairs from MUSE
2. **Orthogonal Procrustes**: Learns optimal rotation matrix between embedding spaces
3. **Cosine Similarity Evaluation**: Measures alignment quality
4. **PCA Visualization**: 2D projection of aligned word pairs

**Result**: English and French word embeddings are mapped to a shared semantic space!

##  Semantic Analysis Tasks

### Task 1: Synonyms & Antonyms (English)
- Find semantically similar words using Word2Vec
- Compare cosine similarity for synonym pairs (e.g., "good" ↔ "nice")
- Measure distance for antonym pairs (e.g., "good" ↔ "bad")

### Task 2: Common Words Across Languages
- Evaluate alignment quality for frequent words
- Examples: "the" ↔ "le", "and" ↔ "et", "for" ↔ "pour"
- Measure cross-lingual cosine similarity

### Task 3: Polysemy Analysis
- Explore multiple meanings of ambiguous words
- Example: "bank" (financial institution vs. river bank)
- Analyze nearest neighbors in embedding space

### Task 4: Out-of-Vocabulary (OOV) Handling
- Compare Word2Vec (fails on rare words)
- Compare GloVe (fails on rare words)
- Compare FastText (handles rare words via subword information)

##  Results and Visualizations

The notebook includes rich visualizations:
- **PCA scatter plots**: 2D visualization of aligned embeddings
- **Cosine similarity heatmaps**: Alignment quality metrics
- **Semantic neighbor analysis**: Word relationships
- **Classification reports**: Downstream task performance

##  Technologies Used

- **NLP Libraries**: NLTK, Gensim
- **Machine Learning**: scikit-learn, SciPy
- **Embeddings**: Word2Vec, FastText, custom GloVe
- **Alignment**: MUSE dictionary, Orthogonal Procrustes
- **Data Processing**: NumPy, pandas
- **Visualization**: matplotlib



##  References

- **Tatoeba Project**: https://tatoeba.org
- **MUSE Embeddings**: Facebook Research
- **Word2Vec**: Mikolov et al., 2013
- **GloVe**: Pennington et al., 2014
- **FastText**: Bojanowski et al., 2017

---

##  Getting Started Now

** to run** Simply open the notebook in Google Colab and execute all cells. The entire pipeline is fully automated and will complete in approximately **10-15 minutes**.
