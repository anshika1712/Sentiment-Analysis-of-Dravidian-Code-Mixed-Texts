# Sentiment Analysis and Homophobia Detection of Code-Mixed Dravidian Languages

This repository contains the implementation of our paper **"Sentiment Analysis and Homophobia Detection of Code-Mixed Dravidian Languages leveraging pre-trained model and word-level language tag,"** presented at DravidianCodeMix 2022 at the Forum for Information Retrieval Evaluation (FIRE) 2022.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Results](#results)
- [Usage](#usage)
- [Contributors](#contributors)

## Introduction
Social media platforms have seen a significant rise in user engagement in recent years. More and more people are expressing their views and ideas on these platforms, creating a need to develop an accurate system to classify text based on sentiments and detect homophobic content. This work focuses on sentiment analysis and homophobia detection in code-mixed Dravidian languages (Tamil-English, Malayalam-English, and Kannada-English). We leverage pre-trained models like mBERT and word-level language tags to classify YouTube comments into various categories.

## Dataset
The dataset used in this project consists of YouTube comments in three code-mixed Dravidian languages. The datasets for sentiment analysis and homophobia detection were provided by the organizers of DravidianCodeMix 2022.

### Data Distribution for Sentiment Analysis
| Language       | Positive | Negative | Mixed Feelings | Unknown State | Not in Language |
| -------------- | -------- | -------- | -------------- | ------------- | --------------- |
| Tamil-English  | 20,070   | 4,271    | 4,020          | 5,628         | 1,667           |
| Kannada-English| 2,823    | 1,188    | 574            | 711           | 916             |
| Malayalam-English| 6,421  | 2,105    | 926            | 5,279         | 1,157           |

### Data Distribution for Homophobia Detection
| Language       | Non-anti-LGBT+ | Homophobic | Transphobic |
| -------------- | -------------- | ---------- | ----------- |
| Tamil-English  | 3,438          | 311        | 112         |
| Tamil          | 2,022          | 485        | 155         |
| English        | 3,001          | 157        | 6           |
| Malayalam      | 2,434          | 491        | 189         |

## Methodology
### Data Pre-processing
- Limiting repeated characters to two contiguous repeats.
- Removing hashtags, punctuation, URLs, numbers, and mentions without clear semantic significance.
- Replacing emojis with their proper semantic text.
- Stripping off any white spaces and extra spaces.

### Model Architecture
We utilized the `bert-base-multilingual-cased` (mBERT) pre-trained model for classification tasks. Our architecture involves:
- Tokenization using HuggingFace's pre-trained BERT tokenizer.
- Fine-tuning mBERT for the specific tasks of sentiment analysis and homophobia detection.
- Training the classifier across 2-4 epochs with a batch size of 32, using the AdamW optimizer and a learning rate of 2e-5.

## Results
Our proposed system achieved the best results for Task A, securing the first rank for Malayalam-English and Kannada-English code-mixed datasets with F1 scores of 0.72 and 0.66, respectively.

## Usage

### Prerequisites
Make sure you have Python 3.x and the necessary libraries installed. You can install the required dependencies using the following command:
```bash
pip install -r pytorchtools.py
```
### Clone the Repository
git clone https://github.com/anshika1712/Sentiment-Analysis-of-Dravidian-Code-Mixed-Texts.git
cd Sentiment-Analysis-of-Dravidian-Code-Mixed-Texts

### Python Notebooks
I have provided notebooks for different stages of our project. You can open and run these notebooks using Jupyter Lab or Jupyter Notebook.

Preprocessing: TaskA_BasicPreprocessing.ipynb and Task_B_Preprocessingipynb.ipynb
This notebook handles data cleaning and preparation.

Training: mBert_model.ipynb
This notebook includes the code to train the mBERT model for sentiment analysis and homophobia detection.

To get the language tags refer LID_Tags.ipynb and for classifying comments into Language or Not in Intended Language refer correct_LID.ipynb
To get the final prediction check out Merging_the_Predictions.ipynb

## Contributors
- Supriya Chanda (supriyachanda.rs.cse18@itbhu.ac.in)
- Anshika Mishra (anshika.mishra2019@vitbhopal.ac.in)

