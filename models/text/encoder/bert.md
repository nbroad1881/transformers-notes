# BERT (Bidirectional Encoder Representations from Transformers)

Original transformer for text after Attention is All You Need.  

## Pre-Training

NSP and MLM

### NSP: Next Sentence Prediction

- Given two sentences (A,B), output 1 if sentence B logically follows sentence A. Otherwise, output 0

### MLM: Masked Language Modeling

- For 15% of the tokens, modify them with the following probabilities:
  - 80% of the time put a [MASK] token. Model must predict actual token
  - 10% put a random token
  - 10% of the time do nothing

BERT saw (1M steps * 256 bs * 512 tokens = 131B tokens) (page 13)

## Data

13GB of Books Corpus + Wikipedia

## Fine-tuning

Typically can be trained to do:

- sequence classification
- token classification
- extractive question answering
- pair classification

## Beware

This model is outdated and there are many newer models that are better, mainly roberta and deberta.

## Links

[arxiv](https://arxiv.org/abs/1810.04805)  
[github](https://github.com/google-research/bert)  
[visualization](https://jalammar.github.io/illustrated-bert/)