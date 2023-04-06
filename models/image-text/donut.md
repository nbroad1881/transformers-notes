# Donut (Document Understanding Transformer) 🍩

Combine image encoder and text decoder for OCR-free document understanding. Can do handwriting and generic documents (letters, receipts, invoices, etc.).

## Model

Swin encoder, mbart decoder with layers removed and vocabulary reduced

## Data

Use Synthdog to generate a bunch of document images. Put text on documents with random backgrounds. Created 0.5M examples each for English, Chinese, Korean, Japanese.

Use IIT-CDIP (11M scanned English documents)

## Pre-Training

Model does OCR on document images. Given an image, do CLM on the text.

## Fine-tuning

Used for document classification, visual qa, parsing (turn receipt into json)

## Beware

- Pre-trained models likely to have [UNK] tokens for English words. The "1" in ">1" will be [UNK].
- The higher the resolution, the better the model should do, but the more memory it will take. 2560×1920 got best results, but this likely requires 80GB GPUs. Other resolutions tried: 1280x960, 960x960, 640x640

## Links
[arxiv link](https://arxiv.org/abs/2111.15664)  
[github repo](https://github.com/clovaai/donut)