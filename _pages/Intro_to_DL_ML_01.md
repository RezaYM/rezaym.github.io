---
layout: archive
title: "Linear Algebra Basics For ML & DL"
permalink: /DLML/Linear_Algebra/
author_profile: true
redirect_from:
  - /DLML
---

{% include base_path %}

We know what vectors and matrices are. Just a set of numbers or objects juxtaposed in a one-dimensional or two-dimensional structures. Now if these numbers are put in three-dimensional or higher-dimensional structures, they are called tensors. We have the following notation:

* Matrix $$\mathcal{A} \in \mathbb{R}^{m\times n}$$ has $$m$$ row and $$n$$ columns. The $$i^{\text{th}}$$ row and $$j^{\text{th}}$$ column of this matrix are shown with $$\mathcal{A}_{i,:} \text{ and } \mathcal{A}_{:,j}$$ respectively.

* Tensor $$\mathbb{A} \in \mathcal{R}^{n_1 \times n_2 \times n_3}$$ is of dimensions $$n_1 \times n_2 \times n_3$$ . $$\mathbb{A}_{i,j,k}$$ is the element of the tensor which is at coordinates $$(i,j,k)$$. $$\mathbb{A}_{i,:,:}$$ is a two-dimensional cut of the tensor.

I think we all are familiar with the transpose and multiplication operations on matrices. Also, the element-wise product operation of matrices which we show with $$\mathbb{A}_1 \odot \mathbb{A}_2$$.
