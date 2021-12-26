---
layout: archive
title: "Problem: Linear Matrix Inequality Solution"
collection: cnvxopt
permalink: /cnvxopt/intextproblem1
---
### Problem:
Prove that set of points $$x$$ satisfying Linear Matrix Inequality is convex: $$x_1 A_1 + \dots + x_n A_n \preceq B$$, with $$A_i , B \in \mathbb{S}^m$$
### Proof: 
Consider the set: $$\{x\| A(x) \preceq B\}$$. If $$x$$ belongs to this set, then $$B-A(x)$$ is Postive Semi Definite matrix. In fact all such matrices form a cone which is convex. 
