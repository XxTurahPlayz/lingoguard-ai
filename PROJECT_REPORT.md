# LingoGuard AI — Project Report

**Hackathon:** Veritas AI International High School Hackathon 2026  
**Track:** AI + Languages  
**Project:** LingoGuard AI

## 1. Problem Statement

Identifying the language of short text messages can be challenging. Short phrases, ambiguous words, names, and informal writing can lead to incorrect predictions.

LingoGuard AI aims to make language identification more useful by detecting four languages and warning users when the model is uncertain.

## 2. Proposed Solution

LingoGuard AI is a machine-learning language identification system supporting:

- English
- Indonesian
- French
- Spanish

It uses character-level TF-IDF features and Logistic Regression to classify text.

An uncertainty detection feature displays a warning when the highest model score is below 0.60, encouraging users to provide more text.

## 3. Dataset and Methodology

**Dataset:** Tatoeba sentence collection.

- 8,000 total sentences.
- 2,000 sentences per language.
- Reservoir sampling with random seed 42.
- Training set: 5,600 sentences.
- Validation set: 1,200 sentences.
- Test set: 1,200 sentences.

**Feature extraction:** Character-level TF-IDF using character n-grams of lengths 1–3.

**Classification:** Logistic Regression with a maximum of 1,500 iterations and balanced class weights.

## 4. Evaluation Results

The model was evaluated using the held-out test set.

| Model | Accuracy | Macro F1 |
|---|---:|---:|
| Majority-class baseline | 25.00% | 0.1000 |
| langdetect | 92.17% | 0.9538 |
| **LingoGuard AI** | **99.33%** | **0.9933** |

LingoGuard correctly classified 1,192 of 1,200 test sentences.

### Confusion Matrix Results

| Actual language | Correct | Incorrect |
|---|---:|---:|
| English | 295 | 5 |
| French | 299 | 1 |
| Indonesian | 298 | 2 |
| Spanish | 300 | 0 |

### Uncertainty Detection

A threshold of 0.60 was evaluated on the validation set:

- Coverage: 96.50%.
- Accuracy among accepted predictions: 100% on this validation sample.

These results do not guarantee perfect predictions on unseen real-world text. Model scores are not calibrated probabilities.

## 5. Error Analysis and Limitations

The model made eight mistakes on the held-out test set.

Examples included:

- "halo dunia!" — Indonesian predicted as Spanish.
- "Our silence says a lot." — English predicted as French.
- "Tory dies." — English predicted as Spanish.
- "Youba habite à Tizi Gheniff." — French predicted as English.

These errors suggest challenges with short text, uncommon words, proper names, and overlapping language patterns.

The system currently supports only four languages. Its performance on code-mixed text and languages outside its supported set has not been established.

## 6. Future Improvements

- Expand support to Malay and additional languages.
- Add informal messages and short-text examples to the dataset.
- Improve handling of proper names and ambiguous phrases.
- Investigate code-mixed language detection.
- Evaluate on independent datasets beyond Tatoeba.
- Further test and tune uncertainty detection.

## 7. Technologies and Credits

- Python
- Google Colab
- pandas
- scikit-learn
- TF-IDF
- Logistic Regression
- langdetect
- Gradio
- Tatoeba sentence collection
- ChatGPT for development assistance and debugging

## 8. Project Links

**GitHub repository:** https://github.com/XxTurahPlayz/lingoguard-ai

**Notebook:** LingoGuard_AI_Hackathon_2026.ipynb

**Demo:** [Add your current Gradio demo link here.](https://f6cf044eec5c8c0886.gradio.live)

**Participant:** I GUSTI NGURAH GANESHA KRISHNA
