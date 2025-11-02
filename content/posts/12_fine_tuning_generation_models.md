---
title: 12 - Fine-Tuning Generation Models
subtitle:
date: 2025-10-09T03:27:17-07:00
slug: fine_tuning_generation_models
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

There are two most common methods for fine-tuning text generation models: *supervised fine-tuning (SFT)* and *preference tuning*. 

## The Three LLM Training Steps: Pretraining, Supervised Fine-Tuning, and Preference Tuning

1. Pretraining: Pretain on one or more massive text datasets, and the goal is to predict the next token to accurately learn linguistic and semantic representations in the text. It is a self-supervised method, and output a base model or foundation model. 

2. Supervised fine-tuning (fine-tuning 1): Adapt the base model to follow instructions. The goal is still to predict the next token but now also based on the **user input**. It is often used to go from a base generative model to an instruction (or chat) generation mdoel. 

3. Preference tuning (fine-tuning 2): Improves the quality of the model and makes it more aligned with the expected behavior of AI safety or human preferences. 

### Parameter-Efficient Fine-Tuning (PEFT)

During fine-tuning, updating ALL parameters of a model has a large potential of increasing its performance but very costly and slow to train, and requires significant storage, so we propose parameter-efficient fine-tuning (PEFT) to focus on fine-tuning pre-trained models at higher computational efficiency. 

1. Adapters: A core component of many PEFT-based techniques, they add a small number of weights in certain places in the network that can be *efficiently* fine-tuned while leaving the majority of the model weights frozen.

2. Low-Rank Adaption (LoRA): A technique that only requires updating a small set of parameters by creating a small subset of the base model to fine-tune. 
