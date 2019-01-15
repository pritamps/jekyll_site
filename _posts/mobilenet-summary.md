---
layout: post
title:  "Paper Review: MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications"
date:   2019-01-15 10:25:00 +0530
categories: deeplearning literature_review
latexscript: js/katex_render.js
---

Very important paper because it paved the way for deep learning on mobile devices, and is maybe the standard on the tradeoffs needed.

**Key development**: Depthwise separable convolutions.

Focus is on reducing latency.

Depthwise separable convolutions are the same building blocks used in Inception networks.

## Background: Residual Blocks

Paper: Deep Residual Networks for Image Recognition.

Helps in training very deep networks by dealing with vanishing/exploding gradients.

The intuition is that the identity function is easy for residual blocks to learn.

## Background: 1x1 convolutions

Paper: Lin et. al, Network in Network (the rest of the paper isn't used much. But the idea of 1x1 convolution is used a lot!)

Can make sort of a network that gives a way to combine information from all the channels in a layer. 

For example, 28x28x192 layer can be shrunk to 28x28x32 by using 32 1x1x192 filters, yeah?

Another thing 1x1 convolutions can do is add a nonlinearity to the network.

## Background: Inception network

Paper: Going deeper with convolutions.

Combining different types of convolutions into one layer, i.e. depthwise separable convolutions!

This means some padding will be needed for pooling layers.


