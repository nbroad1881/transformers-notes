# RoBERTa (Robustly Optimized BERT)

Get better results than BERT by:
1. Only doing MLM instead of MLM+NSP
2. Train on more data (160GB vs 13GB)
3. Train longer 
   - BERT saw (1M steps * 256 bs * 512 tokens = 131B tokens) (page 13)
   - RoBERTa saw (500k steps * 8k bs * 512 tokens = 2T tokens) (page 7)


[arxiv  link](https://arxiv.org/abs/1907.11692)
[github repo](https://github.com/facebookresearch/fairseq/tree/main/examples/roberta)