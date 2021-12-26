---
layout: archive
title: "Notes on Convex Optimization: "
permalink: /cnvxopt/
author_profile: true
---
This page is my summary of [Book](https://web.stanford.edu/~boyd/cvxbook/) by Stephen Boyd an Lieven Vandenberghe on Convex Optimization. 
# Convex Sets
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
* **Notes**: 
  * Interior of a set is considered w.r.t. the whole spece of $$\mathbb{R}^n$$. The interior of a flat disk in 3 dimensional space is empty.
  * The Relative interior is considered w.r.t. the space restricted to affine hull of the set. The relative interior of a flat disk in 3 dimensional space is the disk itself (excluding the edge). 
  * The boundary of a set is considered w.r.t. the whole spece of $$\mathbb{R}^n$$. The boundary of a flat disk is the flat disk itself. 
  * The relative boundary is defined w.r.t. the affine hull. The relative boundary of a flat disk is the edge of the disk. 

## Convex Sets and examples
* *Convex Set*: A set is convex if the segment of the line between any two points of the set lies inside the set. Equivalently we can define *Convex Combination* of a set of points. 
* *Convex Hull* of set $$C$$: convex combination of all points in $$C$$. 
* **Notes**: Difference between convex hull and affine hull is coeffcient $$\theta_i$$ of a point $$x_i$$. In convex hull it is postive; in affine hull we have no restriction on positivity. 
* *Cone*: A set $$C$$ is a cone if $$\theta x \in C$$, $$\forall x \in C$$. *Conic Combination* can be defined equivalently.
 * *Convex Cone*: if both convex and cone. 
 * *Conic hull* of set $$C$$: set of all conic combinations of points in $$C$$:
$$\{\theta_1 x_1 + \dots + \theta_k x_l \| x_i \in C, \theta_i \geq 0, i=1, \dots, k\}$$
* *hyperplane*: $$\{x\|a^T x = b\}$$.
* *halfspace*: $$\{x\|a^T x \leq b\}$$
  * halfspaces arec onvex. They are not affine. Not necessarily cone. Not necessarily subspace. 
  * A hyperplane is actually the set of all points $$x$$, such that $$x-x_0$$ is orthoginal to $$a$$; where $$x_0$$ is a point on the hyperplane. 
* *Euclidean Ball*: $$B(x_c, r) =$$ $$ \{ x \| \|x - x_c\| \leq r\} = \{x\| (x-x_c)^T (x-x_c) \leq r^2 \}$$,
* *Elipsoid*: $$\zeta = $$ $$\{ x\| (x-x_c)^T P^{-1} (x-x_c) \leq r^2 \}$$, with $$P$$ being symmetric and positive definete matrix. 
  * $$P$$ determines how distorted the elipsoid is w.r.t. a ball. 
  * $$\sqrt{\lambda_i}$$ is the length of the semi-axis along each eigenvector of $$P$$, and $$\lambda_i$$ is the relevant eigenvalue. 
  * A ball is an elipsoid with $$P=I$$. 
* *Norm Cone*: for any norm, *Norm Cone* is defined as: $$C = \{(x,t)\| \|x\|\leq t\}$$.
  * Note that x is in $$\mathbb{R}^{n-1}$$ and $$t$$ is the $$n^{\textit{th}}$$ dimension. 
  * For instance, consider euclidean norm: norm cone is the set of flat disks which are mounted on top of each other, the radious of each cone is $$t$$. 
  * It is also called *Lorentz cone* or *ice cream cone*. 
* *Polyhedra*: intersection of finite number of hapspaces and hyperplanes. 
$$\mathcal{P} = \{x \| a_j^T x \leq  b_j, j= 1, \dots, m, c_j^T x = d_j, j=1, \dots, p\}$$.
* *Simplexes*: Assume $$k+1$$ points, $$v_0, v_1, \dots, v_k$$ that are affinely independent: $$v_1-v_0, v_2 - v_0, \dots, v_k - v_0$$ are linearly independent. Simplex: 
$$\mathbb{conv} \{v_0, \dots, v_k\} = \{\theta_0 v_0 + \dots + \theta_k v_k \| \mathbb{\theta} \geq 0, \sum_{i=0}^k \theta_i =1\}$$. Examples: *Unit Simplex*, *Probability Simplex*. 
* Set of *Symmetric Matrices*: $$\mathbb{S}^n = \{X \in \mathbb{R}^{n \times n} \| X = X^T\}$$,
* Set of *positive semidefinite matrices*: $$ \mathbb{S}^n$$<sub>+</sub> $$= \{X \in \mathbb{R}^{n \times n} \| X \succeq 0\}$$,
* Set of *positive matrices*: $$ \mathbb{S}^n$$ <sub>++</sub> $$= \{X \in \mathbb{R}^{n \times n} \| X \succ 0\}$$,

## Operations Preserving Convexity: 
* Intersection: of possibly infinite convex sets is convex. 

