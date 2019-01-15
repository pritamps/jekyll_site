---
layout: post
title:  "Paper Review: MobileNetV2: Inverted Residuals and Linear Bottlenecks"
date:   2019-01-15 10:25:00 +0530
categories: deeplearning literature_review
latexscript: js/katex_render.js
---

Very important paper because it paved the way for deep learning on mobile devices, and is maybe the standard on the tradeoffs needed.


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

Paper: Szegedy et. al, Going deeper with convolutions.

Combining different types of convolutions into one layer, i.e. depthwise separable convolutions! After this, the resultant layer is then passed through <script type="math/tex"> 1 \times 1 </script> convolution to combine.

Other approaches (not studied here):

1. Factorized CNNs
2. Flattened CNNs
3. Squeezenets
4. Structured Transform Networks
5. Deep Fried CNNs

This means some padding will be needed for pooling layers.

Computationally expensive (especially if using large filters such as 5x5 etc.), but 1x1 convolutions can help with this, i.e. bottleneck layers which will reduce the number of channels. 

## Background: MobilenetV1

**Key development**: Depthwise separable convolutions (like inception networks).

Focus is on reducing latency.

Depthwise separable convolutions are the same building blocks used in Inception networks.
Instead of <script type="math/tex"> N </script>  filters of size <script type="math/tex"> D_k \times D_k \times M </script>, we have M filters of <script type="math/tex"> D_k \times D_k \times 1 </script> followed by <script type="math/tex"> N </script> <script type="math/tex"> 1 \times 1 \times M </script> filters. 

With real numbers: first is a <script type="math/tex"> 1 \times 1 </script> convolution first to compress the channels, then a <script type="math/tex"> 3 \times 3 </script> convolution that comes next has fewer parameters to deal with. Then, another <script type="math/tex"> 1 \times 1 </script> channel follows, which allows to match the input and output layer
Parameters:

* The width multipler <script type="math/tex"> \alpha </script> thins the network at every layer. 
* Resolution multiplier <script type="math/tex"> \rho </script> which simply reduce resolution and each layer by <script type="math/tex"> \rho </script> 

## MobileNet V2

MobileNetV1 introduced the use of depthwise separable convolutions. MobileNetV2 uses those adds **Linear Bottlenecks**. What this means is that there is no activation (Relu etc) on the bottleneck layer.

Unlike MobileNetV1, the number of channels if first *increased*, then the the <script type="math/tex"> 3 \times 3 </script> convolution is applied, following which another <script type="math/tex"> 1 \times 1 </script> convolution reduces the number of channels to match the input channel and allow for residual.

The computational efficiency is about the same as MobileNetV1, but the accuracy is higher for the same number of parameters.
