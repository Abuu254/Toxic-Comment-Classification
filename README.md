# Toxic Comment Classification
A machine learning model that’s capable of detecting different types of toxicity like threats, obscenity, insults, and identity-based hate in comments.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1Vni0BgJdlkWwnFoslkJ6GHS98D-WMYK0?usp=sharing)

> **NOTE**: This project uses a large dataset with over 150K data points for training. It's optimized to run on a local machine with the Colab environment due to computational requirements. Running the code on online Colab may encounter issues.

## Table of Contents
- [Context](#context)
- [Dataset](#dataset)
- [Processing Steps](#processing-steps)
- [Model Selection](#model-selection)
- [Modeling Process](#modeling-process)
- [Testing the Model](#testing-the-model)
- [Evaluation and Improvement](#evaluation-and-improvement)
- [Challenges](#challenges)
- [Reflection](#reflection)

## Context
In today's digital age, fostering a respectful online conversation environment is pivotal. This project aims to detect and categorize toxic comments, addressing a rising concern in Natural Language Processing. The primary objective is to devise a machine-learning model to pinpoint various toxicity types like threats, obscenity, insults, and identity-based hate in online text.

## Dataset
The dataset, sourced from [Kaggle](https://www.kaggle.com/competitions/jigsaw-toxic-comment-classification-challenge/data), contains comments from Wikipedia's talk page edits, labeled for toxicity type. It's divided into:
- Training dataset
- Testing dataset
- Testing labels dataset

Columns:
- `id`: Unique comment identifier.
- `comment_text`: Comment's text, the model's input.
- `toxic`, `severe_toxic`, `obscene`, `threat`, `insult`, `identity_hate`: Binary labels indicating comment toxicity.

## Processing Steps
Before modeling, the data underwent:
- Text conversion to lowercase
- Punctuation removal
- Stop words removal
- Lemmatization

## Model Selection
The chosen architecture is a deep learning model with Bi-LSTM and Dense layers, proficient in handling text data. More on model selection can be found in the provided [links](https://www.analyticsvidhya.com/blog/2021/03/introduction-to-long-short-term-memory-lstm/).

## Modeling Process
The comment text data serves as the main feature, tokenized and encoded for the model. Comments can have multiple toxicity labels, posing a multi-label classification challenge. The dataset is split (90% training, 10% validation) to fine-tune model parameters and avert overfitting.

## Testing the Model
Separate training, testing data, and testing labels were provided. The task involved merging the testing data with their labels and removing rows without accurate labeling. The resultant testing data consists of 63,978 points.

## Evaluation and Improvement
The model's performance was evaluated using accuracy, F1-score, precision, recall, and ROC AUC score metrics. For a detailed breakdown, refer to the provided project description.

## Challenges
- **Imbalanced Classes**: Some toxicity classes are more frequent, causing the model to excel with the majority class but falter with the minority.
- **Multi-label Classification**: Comments can fall under multiple toxicity classes, adding complexity.

