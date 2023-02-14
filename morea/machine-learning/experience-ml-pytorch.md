---
title: "5. Pytorch"
published: true
morea_id: experience-ml-pytorch
morea_type: experience
morea_summary: "Pytorch Tutorial"
morea_sort_order: 6
morea_labels:
  - 3:00pm
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How can we model high-dimensional data with deep learning?

**Objectives**
* Understand how to train a neural network in Pytorch
</div>

## Pytorch Tutorial

This is a basic image classification tutorial from CIFAR-10 dataset using Pytorch. 

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **About TensorFlow**
<hr/>

Pytorch is an open source software used in machine learning particularly for training neural networks.

### The CIFAR-10 dataset

CIFAR-10 is a common dataset used for machine learning and computer vision research. It is a subset of 80 million tiny image dataset and consists of 60,000 images. The images are labelled with 10 different classes. So each class has 5000 training images and 1000 test images. Each row represents a color image of 32 x 32 pixels with 3 channels (RGB).

{% include figure.html url="" max-width="50%" file="/morea/hpc/fig/CIFAR-10.jpg" alt="CIFAR" caption="" %}


### Basic workflow of Machine Learning

1. Collect the data
2. Pre-process the data
3. Define a model
4. Train the model
5. Evaluate/test the model
6. Improve your model


{% include next-button.html 
           top-label="Staging and File System Choice ->" 
           bottom-label="3:20pm" 
           url="/morea/hpc/experience-hpc-file-systems.html" %}
