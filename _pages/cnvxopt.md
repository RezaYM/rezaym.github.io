---
layout: archive
title: "Notes on Convex Optimization: "
permalink: /cnvxopt/
author_profile: true
---
### Convex Sets
## Basic Definitions
* *Affine Set*: A set $$C\subseteq \mathbb{R}^n$$ is affine if the line connecting two points in the set belongs to the set: If $$x_1, x_2 \in C$$, then, $$\theta x_1 + (1-\theta) x_2 \in C$$.


* *Affine combination of points*: $$\theta_1 x_1 + \theta_2 x_2 + \dots + \theta_k x_k$$ is the affine combination of points $$x_1, x_2, \dots, x_k$$, with $$\theta_1 + \theta_2 + \dots + \theta_k = 1$$.
* *Subspace*: is closed under sum and scalar multiplication. 
* *Affine hull* of a set $$C\subseteq \mathbb{R}^n$$: smallest affine set containing $$C$$: $$\mathbb{aff} C = \{\theta_1 x_1 + \dots + \theta_k x_k\| \theta_1 + \dots + \theta_k = 1\}$$.
* *Affine Dimension* of set $$C$$: smallest affine set containing $$C$$. 
  * $$C = \{x \in \mathbb{R}^2 \| x_1^2 + x_2^2 = 1\}$$: its affine hull is all of $$\mathbb{R}^2$$ and its affine dimension is 2. 
* *Relative Interior* of set $$C$$: Points of $$C$$ which which belong to the intersection ball with radius $$r>0$$ centering that point and $$\mathbb{aff} C$$:
$$\mathbb{relint} C = \{x \in C \| B(x,r) \cap \mathbb{aff}C \text{ for some } r>0\},$$ 
* *Relative Boundary* of set $$C$$: Closure of $$C \backslash \mathbb{relint} C$$.
