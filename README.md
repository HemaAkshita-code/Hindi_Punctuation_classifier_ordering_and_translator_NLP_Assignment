# Hindi Text Restoration, Sentence Ordering and Translation

## Project Overview

This project aims to process Hindi text containing missing punctuation and shuffled sentences, reconstruct a coherent sequence, group sentences into sets of five, and translate the resulting text into English.

The system is designed as a multi-stage NLP pipeline using locally trained models.

## Approach

### 1. Punctuation Restoration
- Model: AI4Bharat IndicBERT.
- Task: Token classification.
- Predicts punctuation categories:
  - No punctuation
  - Comma-like punctuation
  - Sentence ending
  - Question mark
  - Exclamation mark
- Training data: Hindi Wikipedia with synthetically generated punctuation labels.

### 2. Sentence Ordering
- Model explored: IndicBERT with a pairwise classification head.
- Task: Predict which of two sentences appeared first in the original text.
- Pairwise predictions are intended to be combined to estimate the overall sentence sequence.

### 3. Sentence Grouping
After sentence ordering, consecutive sentences are grouped into sets of five.

### 4. Hindi-to-English Translation
The planned translation component uses a neural machine translation approach. The IIT Bombay English-Hindi parallel corpus (`cfilt/iitb-english-hindi`) was identified as the training dataset.

## Technology Stack
- Python
- PyTorch
- Hugging Face Transformers
- Hugging Face Datasets
- AI4Bharat IndicBERT
- Scikit-learn

## Model Files

Trained model checkpoints and associated files are hosted on Google Drive.

**Google Drive Model Link:** https://drive.google.com/drive/folders/1cBPjTtE5iQ6y9VLse_WzyfpFN8JAc2oZ?usp=sharing

## Assignment Constraints
- No off-the-shelf GPT, Gemini, or Claude models.
- GPU memory usage must remain below 1.5 GB.
- Models are trained or fine-tuned for the required NLP tasks.

## Current Development Status

- Punctuation restoration: Experimental checkpoint trained.
- Sentence ordering: Pairwise and fixed-group approaches explored; reliable ordering is still under development.
- Sentence grouping: Pipeline stage designed.
- Hindi-to-English translation: Training and integration pending.

## Input Data
The provided sample ZIP files are used for testing the complete pipeline.

## Repository Structure

```text
project/
├── punctuation/
├── sentence_ordering/
├── translation/
├── data/
├── notebooks/
├── models/
├── requirements.txt
└── README.md
```
