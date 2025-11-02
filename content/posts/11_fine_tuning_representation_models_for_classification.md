---
title: 11 - Fine-Tuning Representation Models for Classification
subtitle:
date: 2025-10-06T03:27:17-07:00
slug: fine_tuning_representation_models_for_classification
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

## Supervised Classification

In this section, we take a supervised approach to allow both the model and the classification head to be udpated during traning . For example, for a task-specific model, we can fine-tune both the representation model and the classification head as a single architecture as shown below. 

<figure>
  <img src="/images/hands-on-LLM/11-03.png" alt="trainable representation models" width="50%" />
  <figcaption>Fig. A task-specific model architecture with a pretained representation model (BERT) and an additional classification head for the specific task (both are trainable).</figcaption>
</figure>


## Few-Shot Classification

Few-show classification is a technique within supervised classification to have a classifier learn target labels based on only a few labeled examples. It is great when we need to you a classification task but do not have many labeled data points. 


An exmple efficient framework of the few-shot text classifiction is *SetFit* has the following 3 steps: 

1. Sampling training data based on in-class and out-class selection of labeled data
2. Fine-tuning a pretrained embedding model based on the above training data. The goal is to create embeddings that are tuned to the classification task 
3. Train a classifier by creating a classification head on top of the embedding model and train it using the above training data

<figure>
  <img src="/images/hands-on-LLM/11-13.png" alt="SetFit Steps" width="50%" />
  <figcaption>Fig. The 3 main steps of the SetFit (an efficient fine-tuning framework)</figcaption>
</figure>

## Continued Pretraining with Masked Language Modeling

Instead of adopting the two-step approach (e.g., pretain, then fine-tune) above, continued pretaining with masked language modeling add another step between them to **continue training the model with data from our domain**.

## Named-Entity Recognition

Name-entity recoginition (NER) is helpful for de-identification and anonymization tasks when there is sensitive data. It allows for the classification of individual tokens and/or words, including people and locations.
