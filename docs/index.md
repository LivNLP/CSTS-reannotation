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

👉 [**Visit the Huggingface dataset**](https://huggingface.co/datasets/LivNLP/C-STS-Reannotated)

### Load Dataset

Use the code snippet below to access both the **`train`** and **`validation`** splits:

```python
from datasets import load_dataset

# Load the dataset from the Hugging Face Hub
dataset = load_dataset("LivNLP/C-STS_Reannotated")

# Access the training and validation splits
train_data = dataset["train"]
validation_data = dataset["validation"]

# Print an example instance
print(train_data[0])
```

## Citation Information
```bibtex
@inproceedings{zhang-etal-2025-annotating,
    title = "Annotating Training Data for Conditional Semantic Textual Similarity Measurement using Large Language Models",
    author = "Zhang, Gaifan  and
      Zhou, Yi  and
      Bollegala, Danushka",
    editor = "Christodoulopoulos, Christos  and
      Chakraborty, Tanmoy  and
      Rose, Carolyn  and
      Peng, Violet",
    booktitle = "Proceedings of the 2025 Conference on Empirical Methods in Natural Language Processing",
    month = nov,
    year = "2025",
    address = "Suzhou, China",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2025.emnlp-main.1373/",
    doi = "10.18653/v1/2025.emnlp-main.1373",
    pages = "27015--27027",
    ISBN = "979-8-89176-332-6",
    abstract = "Semantic similarity between two sentences depends on the aspects considered between those sentences. To study this phenomenon, Deshpande et al. (2023) proposed the Conditional Semantic Textual Similarity (C-STS) task and annotated a human-rated similarity dataset containing pairs of sentences compared under two different conditions. However, Tu et al. (2024) found various annotation issues in this dataset and showed that manually re-annotating a small portion of it leads to more accurate C-STS models. Despite these pioneering efforts, the lack of large and accurately annotated C-STS datasets remains a blocker for making progress on this task as evidenced by the subpar performance of the C-STS models. To address this training data need, we resort to Large Language Models (LLMs) to correct the condition statements and similarity ratings in the original dataset proposed by Deshpande et al. (2023). Our proposed method is able to re-annotate a large training dataset for the C-STS task with minimal manual effort. Importantly, by training a supervised C-STS model on our cleaned and re-annotated dataset, we achieve a 5.4{\%} statistically significant improvement in Spearman correlation. The re-annotated dataset is available at https://LivNLP.github.io/CSTS-reannotation."
}
```
