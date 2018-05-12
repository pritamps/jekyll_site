---
layout: post
title:  "Paper Review: Gradient-based Learning Applied to Document Recognition"
date:   2018-02-25 10:25:00 +0530
categories: deeplearning literature_review
latexscript: js/katex_render.js
---

Paper being reviewed: *Paper Review: Gradient-based Learning Applied to Document Recognition*
Authors: Yann LeCun, Leon Bottou, Yoshua Bengio, and Patrick Haffner

Landmark paper because the network really worked and showed that you could do image recognition at a pixel level instead of feature extraction.

Later sections cover word handwriting recognition, which requires segmentation of digits. We don't care about that, do we?

Notation is weird throughout the paper
Important section: Convolutional Neural Networks for Isolated Character Recognition

More things covered: segmentation of written work into individual digits.

This post assumes you already know about convolutions and pooling. Until I write my own post about those things, [this](https://cs231n.github.io/convolutional-networks/) is a great resource.

## Sections

### Introduction
  
Covers different ML types:

1. Learning from Data: Minimize a loss function defined as an extension of the error on the training set with a regularisation function. They call this Structural Risk Minimization
2. Gradient based learning: The above loss function is minimised using normal or stochastic gradient descent.
3. Gradient back-propagation: Allows for efficient computation of derivatives in a nonlinear multi-layer processing pipeline (such as a neural network).
4. Learning in Handwriting Recognition Systems: Most challenging part is separating digits. One algorithm is heuristic over segmentation, where random cuts are generated over the training set and used to label characters versus not-characters. Then on the test sets, correct cuts can be found. Very expensive in all ways. Another is Graph Transformer Networks, introduced in this paper. We will come back to this. For segmentation, they just sweep over the image (convolutional style) and choose parts that contain a character.
5. Globally Trainable Systems: Error is defined at document level (a global error). Typically recognition at word level treats words as acyclic graphs, with each edge and node giving the label and probability of the current character (like a HMM)


### Convolutional Neural Networks for Isolated Character Recognition
  
The main section which introduces LeNet-5!

### Results

LeNet did well yay. On isolated characters

### Graph Transformer Networks

Backpropagation for multi-module networks.

### Heuristic Over Segmentation

Problem of separating digits and/or letters in handwriting

### Global training

Heuristic Over Segmentation gives error at character level. Global training takes this error to string level without individual character naming.
  
### Space Displacement Neural Network

Cool idea

### Crazy Math Section

### Conclusions




