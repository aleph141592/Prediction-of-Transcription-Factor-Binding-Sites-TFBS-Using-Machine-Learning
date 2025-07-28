## Prediction-of-Transcription-Factor-Binding-Sites-TFBS-Using-Machine-Learning
This project predicts Transcription Factor Binding Sites (TFBS) using machine learning. We processed FASTA files from two databases (collecTF and RegulonDB), trained both Random Forest and SVM models, and found that SVM performed better in classification accuracy.

## Data Preprocessing Pipeline

### 1. Sequence Standardization
- **Input**: Variable-length DNA sequences (FASTA format)
- **Padding**: Added "N" characters to normalize all sequences to mean length of this chains
- **Goal**: Enable uniform feature extraction without biological distortion

### 2. Numerical Encoding (DDS)
- **Method**: Dinucleotide frequency quantification
- **Output**: Statistical matrix of base-pair adjacency frequencies  
  *(Example: "ATCG" → AA:0, AT:1, TC:1, CG:1)*

### 3. Dataset Augmentation
- **Negative Samples**: Created by random shuffling of original sequences
- **Class Balance**: 1:1 ratio of positive/negative TFBS examples
