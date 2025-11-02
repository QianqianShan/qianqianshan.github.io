---
title: 10 - Creating Text Embedding Models
subtitle:
date: 2025-10-05T03:27:17-07:00
slug: creating_text_embedding_models
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

## Embedding Models

Embedding models are used to process the textual inputs into numerical representations (embeddings) for further processing. One major technique to training, find-tune, and guide embedding models is the *contrastive learning*. Its idea is that the best way to learn and model similarity/dissimilarity between documents is by feeding a model examples of similar and dissimilar paris, so the model can learn from on to keep similar docs closer in vector space while dissimilar ones further apart. Two things are needed in order to perform contrastive learning: 

1. The data that constitues similar/dissimilar paris 
2. How the model defines and optimizes similarity 
