# 🌍 LingoGuard AI

**AI-powered language identification with uncertainty detection.**

LingoGuard AI identifies four languages:
- 🇮🇩 Indonesian
- 🇬🇧 English
- 🇫🇷 French
- 🇪🇸 Spanish

## How it works
LingoGuard uses character-level TF-IDF features and Logistic Regression to identify the language of a text.

It also includes an uncertainty warning when the model's top score is below 0.60.

## Test results

| Model | Accuracy |
|---|---:|
| Majority baseline | 25.00% |
| langdetect | 92.17% |
| LingoGuard AI | **99.33%** |

Evaluated on a held-out test set of 1,200 Tatoeba sentences.

## Technologies
Python · scikit-learn · pandas · Gradio · Google Colab

## Project status
Built for the Veritas AI International High School Hackathon 2026.

## Limitations
Currently supports four languages. Short, ambiguous, and unfamiliar text may be misclassified.
