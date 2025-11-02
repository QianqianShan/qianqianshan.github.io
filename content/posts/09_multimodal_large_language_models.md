---
title: 9 - Multimodal Large Language Models
subtitle:
date: 2025-10-02T03:27:17-07:00
slug: multimodal_large_language_models
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

We explore how images are converted to numerical representations via an adaption of the original transformer technique, and show how LLMs can be extended to include vision tasks.

## Transformers for Vision

Vision Transformer (ViT) is used to transform the unstructured data such as an image into representations that can be used for various tasks (e.g., classification on if an image has a cat in it). It works as follows: 

1. Convert an image into patches of images (e.g., convert a 512 by 512 pixels image into 16 by 16 patches)
2. Linearly embed the patches to create numerical representations (i.e., embeddings) that can be used as the input of the transformer model 

<figure>
  <img src="/images/hands-on-LLM/09-05.png" alt="ViT" width="50%" />
  <figcaption>Fig.Main algorithm of ViTs.</figcaption>
</figure>

## Multimodal Embedding Models

Contrastive language-image pre-training (CLIP) is a multimodal embedding model that connects text and images. It first encode both the image and text (the caption of the image) with imasge and text encoders, respectively, then train to optimize for similarity between the embeddings (i.e., maximize similarity for similar image/caption pairs and minimize for dissimilar pairs). 

