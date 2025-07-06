## Multi-Class-and-Multi-Label-Classification-for-Anuran-Calls-Dataset

This project uses Support Vector Machines (SVMs) to classify frog calls (Anuran calls) into multiple taxonomic levels: Family, Genus, and Species. The task involves multi-class and multi-label classification using the Anuran Calls (MFCCs) dataset.

## 📂 Dataset

- Source: [Anuran Calls (MFCCs) Data Set (UCI ML Repository)](https://archive.ics.uci.edu/dataset/406/anuran+calls+mfccs)

- Features: Mel-frequency cepstral coefficients (MFCCs) extracted from audio recordings of frog calls

- Labels (Multi-label):

  - Family (e.g. Leptodactylidae)

  - Genus (e.g. Adenomera)

  - Species (e.g. AdenomeraAndre)

- Dataset size: 10,219 instances

## 📝 Problem Statement

- Goal: Classify Anuran calls into their correct Family, Genus, and Species using SVMs.

- Challenge: Each instance can belong to multiple levels (Family → Genus → Species). This makes it both a multi-class and multi-label problem.

## 🧪 Project Workflow

# 1. Data Preparation

- Randomly split dataset:

  - Train set: 70%

  - Test set: 30%

- Experiments conducted:

  - On raw attributes

  - On normalized attributes

# 2. Multi-Label Evaluation Metrics

- Implemented metrics for multi-label classification:

- Exact Match Ratio (Subset Accuracy):
- 
  - Fraction of samples where all labels are correctly predicted.

- Hamming Loss / Hamming Score:

  - Measures the fraction of misclassified labels.

# 3. SVM Classifiers

# (a) Gaussian Kernel SVMs

- Trained one-vs-all SVM for each label:

  - Family

  - Genus

  - Species

- Tuned hyperparameters:

  - C (penalty weight)

  - γ (RBF kernel width)

- 10-fold cross-validation for parameter selection

# (b) L1-Penalized SVMs

- Repeated experiment with L1-penalized SVMs

- Attributes normalized before training

# (c) Handling Class Imbalance

- Repeated experiments with SMOTE oversampling for minority classes

- Evaluated impact on:

  - Accuracy

  - Exact match

  - Hamming loss
 
# 💡 Key Insights

- Normalizing attributes significantly improved classification performance.

- SMOTE oversampling mitigated class imbalance, especially for rare species.

- Gaussian kernel SVMs performed better for higher label granularity (species-level classification).

# 🔧 Libraries

- scikit-learn

- imbalanced-learn

- pandas

- numpy

- matplotlib

