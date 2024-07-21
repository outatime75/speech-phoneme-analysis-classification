# Speech Phoneme Analysis and Classification 📊🗣️

## Overview
This project focuses on analyzing and classifying phonemes from speech recordings. Five accents were selected: brm_001, gla_001, lvp_001, roi_001, and sse_001. For each accent, recordings of 5 males and 5 females pronouncing the words "hard," "head," and "hoed" were analyzed. The study targeted the vowel phonemes AA, EH, and OW.

## Tools Used
- **Ocenaudio**: To identify the start and end times of each word.
- **Praat**: To extract the first, second, and third formants from the selected phoneme sequences.
- **Scikit-learn**: For implementing and evaluating the KNeighborsClassifier.

## Key Steps
1. **Data Preparation**: Located and annotated phoneme sequences in the recordings.
2. **Classifier Optimization**: 
   - Evaluated the performance with different values of \( K \).
   - Assessed different distance metrics.
3. **Gender Analysis**: Examined the performance of the classifier on male-only, female-only, and combined datasets.
4. **Error Analysis**: Identified problematic vowels and conducted a detailed statistical analysis.

## Findings

### Changing Values of \( K \) 📈
- The baseline classifier with \( K = 5 \) was optimized.
- Best performance:
  - **F1 Score**: 0.8413 with \( K = 7 \)
  - Improved to **0.8618** with \( K = 6 \) and a specific random state for data split.

### Distance Metrics 📏
- Tested multiple metrics including 'canberra', 'chebyshev', 'cityblock', 'correlation', 'cosine', and 'sqeuclidean'.
- **Best Performance**: Achieved with the Minkowski (Euclidean) distance metric.

### Gender Analysis 👫
- **Combined Dataset**: F1 Score = 0.8618
- **Male-only**: F1 Score = 0.8371
- **Female-only**: F1 Score = 0.9521

### Problematic Vowels 🔤
- **Most Difficult**: OW phoneme in "hoed".
- **Confusion Matrix Analysis**:
  - **OW Phoneme**: F1 Score = 0.82, Precision = 0.9, Recall = 0.75
  - **AA Phoneme**: Higher accuracy with an F1 Score = 0.93

### Additional Work 🛠️
- Suggested improvements:
  - Experiment with other classification algorithms and ensembling methods.
  - Implement cross-validation for better generalization.
  - Increase dataset size and feature set (e.g., more formants, pitch, spectral, and temporal features).

---

This analysis provides a comprehensive approach to phoneme classification, highlighting the influence of different parameters and the importance of gender-based performance differences. 📊🔍
