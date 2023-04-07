# MatCha (**Mat**h reasoning and **Cha**rt derendering pretraining)

## Model description

Image encoder and text decoder. Initialized from pix2struct checkpoint. Does much better than Donut and pix2struct on ChartQA and PlotQA.

### From page 2:

> To summarize, our contributions are: (1) proposing a set of effective pretraining tasks for visual language learning (2) demonstrating consistent improvements across all evaluated tasks and SOTA results on ChartQA, PlotQA, and Chart-to-Text summarization (Statista set) without accessing the gold data tables; (3) verify that MATCHA pretraining transfers to visual language benchmarks beyond the chart & plot domains and achieve SOTA across a wide range of datasets beyond the chart domain such as textbook VQA and Widget Captioning; (4) comprehensive ablations to understand the effect of each pretraining component and its impact to downstream performance. 

## Pre-Training

### Chart de-rendering

Given a chart, generate the data into a table or the code used to create the chart.

### Math reasoning

A huge dataset of problems like this:

```text
'question': "b'Solve -282*d + 929 - 178 = -1223 for d.\\n'"

'answer': "b'7\\n'"
```

Problems are for algebra, calculus, trigonometry, geometry, etc.

## Links

[hf hub](https://huggingface.co/google/matcha-base)  
[arxiv](https://arxiv.org/abs/2212.09662)  
no github known
