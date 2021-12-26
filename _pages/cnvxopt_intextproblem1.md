---
layout: archive
title: "Problem: Linear Matrix Inequality Solution"
collection: cnvxopt
permalink: /cnvxopt/intextproblem1
---
### Problem:
Prove that set of points $$x$$ satisfying Linear Matrix Inequality is convex: $$x_1 A_1 + \dots + x_n A_n \preceq B$$, with $$A_i , B \in \mathbb{S}^m$$
### Proof: 
Consider the set: $$C = \{x\| A(x) \preceq B\}$$. If $$x$$ belongs to this set, then $$B-A(x)$$ is Postive Semi Definite matrix. In fact all such matrices form a cone which is convex. $$C$$ is the inverse image of this cone under the affine function 
$$f: \mathbb{R}^n \longrightarrow \mathbb{S}^m, f(x) = B- A(x)$$.

# Other relevant problem: proof for convexity of ellipsoid: 
Prove that ellipsoid is covex: $$\zeta = \{x \| (x-x_c)^T P^{-1} (x-x_c) \leq 1\}$$.
### Proof: 
Ellipsoid is the invese image of unit ball under the affine mapping $$f(x) = P^{-1/2}(x-x_c)$$.
