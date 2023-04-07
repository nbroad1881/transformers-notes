# MatCha (**Mat**h reasoning and **Cha**rt derendering pretraining)

## Model description

Image encoder and text decoder. Initialized from pix2struct checkpoint. Does much better than Donut and pix2struct on ChartQA and PlotQA. MatCha does better than pix2struct on some pix2struct tasks. SoTA as of end of 2022.

### From page 2:

> To summarize, our contributions are: (1) proposing a set of effective pretraining tasks for visual language learning (2) demonstrating consistent improvements across all evaluated tasks and SOTA results on ChartQA, PlotQA, and Chart-to-Text summarization (Statista set) without accessing the gold data tables; (3) verify that MATCHA pretraining transfers to visual language benchmarks beyond the chart & plot domains and achieve SOTA across a wide range of datasets beyond the chart domain such as textbook VQA and Widget Captioning; (4) comprehensive ablations to understand the effect of each pretraining component and its impact to downstream performance. 

## Pre-Training

40% chart de-rendering, 40% math reasoning, 20% screenshot parsing (like pix2struct) (page 4, section 4.1). 100k steps at bs 512. 

### Chart de-rendering

Given a chart, generate the data into a table or the code used to create the chart. When dropping the code portion as a pre-training task, the model's performance dropped (page 8)

### Math reasoning

MATH: A huge (millions) dataset of problems like this

```text
'question': "b'Solve -282*d + 929 - 178 = -1223 for d.\\n'"

'answer': "b'7\\n'"
```

Problems are for algebra, calculus, trigonometry, geometry, etc.

DROP: 96k QA pairs


## Beware

There are no token inputs to the model. To prompt it, the text must be rendered and placed on the image.


## Links

[hf hub](https://huggingface.co/google/matcha-base)  
[arxiv](https://arxiv.org/abs/2212.09662)  
no github known
