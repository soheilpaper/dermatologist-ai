[//]: # (Image References)

[image1]: ./images/skin_disease_classes.png "Skin Disease Classes"
[image2]: ./images/cat_1.jpeg "Category 1 Rankings"
[image3]: ./images/cat_2.jpeg "Category 2 Rankings"
[image4]: ./images/cat_3.png "Category 3 Rankings"
[image5]: ./images/sample_ROC_curve.png "Sample ROC curve"
[image6]: ./images/sample_confusion_matrix.png "Sample confusion matrix"
[image7]: ./images/final_ROC_curve.png "Final ROC curve"
[image8]: ./images/multi-model_multi-crop_stats.png "Multi-model statistics"

# Dermatologist AI

## Table of Contents
1. [Introduction](#introduction)
2. [My own algorithm](#my-own-algorithm)
3. [Getting Started](#getting-started)
4. [Create a Model](#create-a-model)
5. [Evaluation](#evaluation)
6. [Getting your Results](#getting-your-results)


## Introduction

In this mini project, you will 

The data and objective are pulled from the [2017 ISIC Challenge on Skin Lesion Analysis Towards Melanoma Detection](https://challenge.kitware.com/#challenge/583f126bcad3a51cc66c8d9a).  As part of the challenge, participants were tasked to design an algorithm to diagnose skin lesion images as one of three different skin diseases (melanoma, nevus, or seborrheic keratosis).  

In this project, I have designed an algorithm that can visually diagnose [melanoma](http://www.skincancer.org/skin-cancer-information/melanoma), the deadliest form of skin cancer.  In particular, the algorithm distinguish this malignant skin tumor from two types of benign lesions ([nevi](http://missinglink.ucsf.edu/lm/dermatologyglossary/nevus.html) and [seborrheic keratoses](https://www.aad.org/public/diseases/bumps-and-growths/seborrheic-keratoses)). 

![Skin Disease Classes][image1]

## My own algorithm

Open [my Jupyter Notebook dermatologist-ai.ipynb](dermatologist-ai.ipynb) to see how I trained a Convolution Neural Network to classify the three skin diseases and reached a __Mean ROC AUC score of 0.944__ (see ROC curves for melanoma and seborrheic keratosis below). It would have been a __TOP 1__ in the challenge (see scores in [Evaluation](#evaluation)). It's very satisfying for what I wanted to achieve, especially since the __winner's score is 0.911__.  😃

![Final ROC curve][image7]

But much more than this score, I learned a lot and sometimes the hard way, and took a lot of fun. 😅

Particularly, I share how I turned my many mistakes while designing the model into positive learning experiences!

The Jupyter Notebook was run on [Google Colab](https://colab.research.google.com/) with GPU activated.

## Multi-model statistics

I also found very interesting to make some statisticts on multi-crop / multi-model scores.

A picture is worth a thousand words! Here's the distributions of ROC AUC with respect to number of models:

![Multi-model statistics][image8]

This is interesting to see that __multi-model gives me ≃3.25% return over investment__... whereas multi-crop "only" gives ≃0.6%.

## Getting Started

Click the link below to open notebook in Google Colab:
[<img src="https://colab.research.google.com/assets/colab-badge.svg">](https://colab.research.google.com/github/sebastienlange/dermatologist-ai/blob/master/dermatologist_ai.ipynb)

Then press Ctrl+F9 to Execute all cells in the notebook

Be patient, it takes 12 minutes(\*) to execute all the notebook cells: 
- Download (5') and extract (3') default images
- Download (1') and extract additional images
- Download results for all pretrained models (1')
- Build the best team (1')
- All other cells (1')
_(*) timing is of course approximate_

Add +/- 16 minutes if you want to skip loading results and force testing, because the very first time it will need to resize all images.
And 1 minute to test DenseNet, and up to 4 minutes for NasNetALarge...

Add many hours if you want to train your own model... 😊

If you want to know more details about the challenge itself, or create your own project from scratch, read the [original README.md](https://github.com/udacity/dermatologist-ai/blob/master/README.md).
