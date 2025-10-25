---
layout: default
title: Annotating Training Data for Conditional STS Measurement using LLMs
nav_order: 1
has_toc: true
---

## Introduction
Semantic Textual Similarity (STS) is a core NLP task, but judgments often depend on *which aspect* of the sentences is being compared. To address this, the **Conditional STS (C-STS)** task was proposed, where sentence pairs are evaluated under explicit conditions (e.g., *number of people*, *color of objects*).  

However, the original C-STS dataset contained **ambiguous and inconsistent condition statements** as well as **noisy similarity ratings**, which limited model performance.

## Our Work
In this paper (EMNLP 2025), we present a **large-scale re-annotated C-STS dataset** created with the assistance of Large Language Models (LLMs).  

- We first **refine condition statements** to remove ambiguity and grammatical issues.  
- Then we use **GPT-4o** and **Claude-3.7-Sonnet** to re-annotate similarity scores, combining their judgments with the original human labels.  
- The resulting dataset is **more accurate, balanced, and reliable** for training C-STS models.  

## Key Results
- Our re-annotated dataset achieves a **5.4% improvement** in Spearman correlation.  
- Models trained on our dataset reach **73.9% correlation** with human-labeled test data.  
- This resource substantially improves **robustness and consistency** in conditional similarity measurement.  

## Download
The re-annotated dataset is released to support further research in conditional semantic similarity.  

👉 [**Download C-STS Re-annotated Dataset**](dataset.zip)

## Hugging Face Hub

We have published the re-annotated dataset on the **Hugging Face Hub**. Users can easily load and utilize the data directly through the `datasets` library.

### Dataset Card

👉 [**Visit the Huggingface dataset**](https://huggingface.co/datasets/LivNLP/C-STS_updated)

### Load Dataset

Use the code snippet below to access both the **`train`** and **`validation`** splits:

```python
from datasets import load_dataset

# Load the dataset from the Hugging Face Hub
dataset = load_dataset("LivNLP/C-STS_updated")

# Access the training and validation splits
train_data = dataset["train"]
validation_data = dataset["validation"]

# Print an example instance
print(train_data[0])
```

## Citation Information
```bibtex
@misc{zhang2025annotatingtrainingdataconditional,
    title={Annotating Training Data for Conditional Semantic Textual Similarity Measurement using Large Language Models}, 
    author={Gaifan Zhang and Yi Zhou and Danushka Bollegala},
    year={2025},
    eprint={2509.14399},
    archivePrefix={arXiv},
    primaryClass={cs.CL},
    url={https://arxiv.org/abs/2509.14399}, 
}
```
