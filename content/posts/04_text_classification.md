---
title: 4 - Text Classification
subtitle:
date: 2025-09-17T03:27:17-07:00
slug: text_classification
draft: false
author:
  name: Qianqian
  link:
  email:
  avatar:
description:
keywords:
license:
comment: false
weight: 0
tags:
  - LLM
categories:
  - hands-on large language models
hiddenFromHomePage: false
hiddenFromSearch: false
hiddenFromRelated: false
hiddenFromFeed: false
summary:
resources:
  - name: featured-image
    src: featured-image.jpg
  - name: featured-image-preview
    src: featured-image-preview.jpg
toc: true
math: false
lightgallery: false
password:
message:
repost:
  enable: true
  url:

---

<!--more-->

Classifying text is used across a wide range of applications, from sentiment analysis and intent detection to extract entities and detect language. This chapter discusses different ways to use language models for classifying text such as using representation models or generative models.

## Text Classification with Representation Models

Two types of classification with representation models based on fine-tuned foundation model:

1. Task-specific model: a representation model trained for a specific task such as sentiment analysis.
2. Embedding model: a representation model that generates general-purpose embeddings that can be used for a variety of tasks such as classification and semantic search.

<figure>
  <img src="/images/hands-on-LLM/04-4.jpg" alt="classification with representation models" width="50%" />
  <figcaption>Fig. Classification with representation models can be performed either directly with a task-specific model or indirectly with general-purpose embeddings.</figcaption>
</figure>

## Model Selection

Factors that should take into consideration when selecting proper model:

- Choose the model that fits your *use case*
- Consider the *language compatibility*
- The underlying architecture: encoder-only (e.g., BERT) or decoder-only (e.g, GPT)
- Model size: encoder-only models tend to be smaller in size
- Performance
- Inference speed

## Classification Tasks That Leverage Embeddings

Steps:

1. Use embedding model to generate features
2. Feed the features into a classifier for classification

### What If We Do Not Have Labeled Data?

For cases when we have no labeled data, we can use **zero-shot classification** to predict the labels of the input text, and this will also help us to test if it is worthwhile to collect the labels, which is usually resource-intensive.

1. Describe the labels based on what they should represent (e.g., a negative label for movie reviews can be described as "this is a negative movie review")
2. Create label embeddings based on the description (encoding)
3. Assign labels to documents (input) by comparing the similarity between the document and the labed encodings

<figure>
  <img src="/images/hands-on-LLM/04-14.jpg" alt="zero-shot classification" width="50%" />
  <figcaption>Fig. To embed labels, we first give them a description, then embed the description via sentence-transformer.</figcaption>
</figure>


## Text Classification with Generative Models

How is it different with the classification of the representation models? As shown in the diagram, a task-specific model (with representations) generate *numerical* values from tokens, while the generative model generates sequence of tokens that contain the classification results via prompt (or instruction) to guide the process.

<figure>
  <img src="/images/hands-on-LLM/04-17.jpg" alt="compare representation and generative models for classfication" width="50%" />
  <figcaption>Fig. Compare representation (sequence-to-value) and generative models (sequence-to-sequence) for classfication.</figcaption>
</figure>
