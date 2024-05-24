# Advanced Named Entity Recognition for Psychiatric Treatment Reviews

This repository contains the implementation of a Named Entity Recognition (NER) system designed to identify adverse events (AE) and signs, symptoms, and indications (SSI) in psychiatric drug reviews. The project leverages both Conditional Random Fields (CRF) and Bi-LSTM models to achieve high accuracy in entity recognition.

<p align="center">
  <img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*JEQPQQJ8ihUWyVECXLytZg.png" alt="NER Example">
</p>

## Introduction

The goal of this project is to develop a robust NER system to extract and classify entities related to adverse drug events and symptoms from psychiatric treatment reviews. The project explores both traditional machine learning (CRF) and deep learning (Bi-LSTM) approaches to achieve high performance.

## Dataset

The dataset consists of patient reviews for four psychiatric medications: Zoloft, Lexapro, Cymbalta, and Effexor XR. Reviews are split into sentences and labeled using the BIO scheme:
- **B-AE**: Beginning of an adverse event
- **I-AE**: Inside an adverse event
- **B-SSI**: Beginning of a sign/symptom/indication
- **I-SSI**: Inside a sign/symptom/indication
- **O**: Outside any named entity

- **Training Set**: 4,744 sentences from 711 reviews
- **Test Set**: 1,259 sentences from 180 reviews

## Models

### Conditional Random Fields (CRF)
<p align="center">
  <img src="https://media.springernature.com/lw1200/springer-static/image/art%3A10.1186%2Fs12911-019-0865-1/MediaObjects/12911_2019_865_Fig2_HTML.png" alt="BiLSTM Architecture">
</p>
The CRF model was enhanced with additional features such as part-of-speech tagging, word capitalization, and word shape patterns.

### Bi-LSTM
<p align="center">
  <img src="https://production-media.paperswithcode.com/methods/Screen_Shot_2020-05-25_at_8.54.27_PM.png" alt="BiLSTM Architecture">
</p>

The Bi-LSTM model was optimized by:
- Increasing the number of LSTM layers
- Using pre-trained word embeddings
- Applying dropout regularization

## Preprocessing

Data preprocessing included:
- Tokenizing sentences
- Aligning token and tag sequences
- Handling multiple entity tags within sentences

## Feature Engineering

For the CRF model:
- Part-of-speech tags
- Word capitalization
- Word shape patterns

For the Bi-LSTM model:
- Pre-trained word embeddings
- Additional LSTM layers
- Dropout regularization

## Results

The performance of the models was evaluated using precision, recall, and F1-score metrics.

### CRF Model
- **F1-Score**: 0.80 (improved from baseline 0.72)

### Bi-LSTM Model
- **Accuracy**: 88%
- **F1-Score**: 0.85 (improved from baseline 0.78)


## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

