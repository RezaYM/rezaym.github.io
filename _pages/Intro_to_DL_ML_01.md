---
layout: archive
title: "Linear Algebra Basics For ML & DL"
permalink: /DLML/Linear_Algebra/
author_profile: true
redirect_from:
  - /DLML
---

{% include base_path %}
## Introduction for Introduction

We know what vectors and matrices are. Just a set of numbers or objects juxtaposed in a one-dimensional or two-dimensional structures. Now if these numbers are put in three-dimensional or higher-dimensional structures, they are called tensors. We have the following notation:

* Matrix $$\mathcal{A} \in \mathbb{R}^{m\times n}$$ has $$m$$ row and $$n$$ columns. The $$i^{\text{th}}$$ row and $$j^{\text{th}}$$ column of this matrix are shown with $$\mathcal{A}_{i,:} \text{ and } \mathcal{A}_{:,j}$$ respectively.

* Tensor $$\mathbb{A} \in \mathcal{R}^{n_1 \times n_2 \times n_3}$$ is of dimensions $$n_1 \times n_2 \times n_3$$ . $$\mathbb{A}_{i,j,k}$$ is the element of the tensor which is at coordinates $$(i,j,k)$$. $$\mathbb{A}_{i,:,:}$$ is a two-dimensional cut of the tensor.

I think we all are familiar with the transpose and multiplication operations on matrices. Also, the element-wise product operation of matrices which we show with $$\mathbb{A}_1 \odot \mathbb{A}_2$$.

## Span of Vectors

I assume you know what is **[linear independence of vectors](https://en.wikipedia.org/wiki/Linear_independence)**. **Linear combination** of the set of vectors $$\{v^{(1)}, v^{(2)}, \dots ,v^{(n)}\}$$ is given by $$\sum_{i =1}^n c_i v^{(i)} $$, where $$c_i$$s are real coefficients. Set of all points that can be obtained by $$\sum_{i =1}^n c_i v^{(i)} $$ (for some $$c_i \in \mathbb{R}, i \in \{1,\dots, n\}$$) is called the **span** of this set $$\{v^{(1)}, v^{(2)}, \dots ,v^{(n)}\}$$. 
