---
layout: default
title: Annotating Training Data for Conditional STS Measurement using LLMs
nav_order: 1
---

## Introduction {#introduction}
Semantic Textual Similarity (STS) is a core NLP task, but judgments often depend on *which aspect* of the sentences is being compared. To address this, the **Conditional STS (C-STS)** task was proposed, where sentence pairs are evaluated under explicit conditions (e.g., *number of people*, *color of objects*).  

However, the original C-STS dataset contained **ambiguous and inconsistent condition statements** as well as **noisy similarity ratings**, which limited model performance.

## Our Work {#our-work}
In this paper (EMNLP 2025), we present a **large-scale re-annotated C-STS dataset** created with the assistance of **Large Language Models (LLMs)**.  

- We first **refine condition statements** to remove ambiguity and grammatical issues.  
- Then we use **GPT-4o** and **Claude-3.7-Sonnet** to re-annotate similarity scores, combining their judgments with the original human labels.  
- The resulting dataset is **more accurate, balanced, and reliable** for training C-STS models.  

## Key Results {#key-results}
- Our re-annotated dataset achieves a **5.4% improvement** in Spearman correlation compared to the previous state-of-the-art.  
- Models trained on our dataset reach **73.9% correlation** with human-labeled test data.  
- This resource substantially improves **robustness and consistency** in conditional similarity measurement.  

## Download {#download}
The re-annotated dataset is released to support further research in conditional semantic similarity.  

👉 [**Download C-STS Re-annotated Dataset**](dataset.zip)

