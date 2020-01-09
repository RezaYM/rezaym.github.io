---
layout: archive
title: "Introduction to Online Learning"
permalink: /OL/
author_profile: true
redirect_from:
  - /OL
---

{% include base_path %}

In this page, I will present a very basic version of the online learning problem. By going through this page, 
you will  have a sense about the problem and maybe start exploring harder versions by yourself.

**Note 1**: The materials presented here, is mostly based on the "Online Learning" course (IE498) taught by  Professor Yuan Zhou and
my own knowledge of this topic. 

#### Problem Statement
Suppose there are two slot machines: Machine 1 and Machine 2. Whenever, the machine $$i$$ is played, a random reward between $$0$$ and $$1$$ of $$D_i$$ is obtained, such that 

$$\mu_i=E[D_i]$$, $$i=1,2$$

The goal is to detect the arm with higher expected value (higher $$\mu_i$$) is to play each arm equal times, say $$T/2$$ times for a given time horizon of $$T$$, and output the arm with the better empirical mean. The following algorithm uses this method:

*AlG1:*

Step 1: Play arm 1 $$T/2$$ times and then play arm 2 $$T/2$$ times.

Step 2: Calculate empirical means $$\hat \mu_1,\hat \mu_2$$ and output $$\arg\min_{i=1,2}\{\hat \mu_i\}$$.

When performing algorithm one, its success in detecting the better arm is dependent on the distance between the values of $$\mu_1$$ and $$\mu_2$$. In other words, if the distance is large enough, then our confidence about the result of ALG1 is more than the case when $$\mu_1$$ and $$\mu_2$$ are close to each other. For instance, when $$\mu_1 =0.1$$ and $$\mu_2 = 0.8$$ we can be sure about the correctness of output in *ALG1* more than the situation where $$\mu_1 = 0.49$$ and $$\mu_2 = 0.51$$.

Denote $$\Delta = \|\mu_1 - \mu_2\|$$. The following result shows that ALG1 outputs the correct arm (the better arm) with high probability and this probability is a function of $$\Delta$$.


**Theorem 1:** ALG1 outputs the better arm with probability at least $$1-4\exp( -\Delta^2T/4)$$.

**Proof:** WLOG, assume $$\mu_1>\mu_2$$. Denote $$\Delta=\|\mu_1-\mu_2\|$$. By Hoeffding's inequality,

$$\Pr \{|\mu_i-\hat \mu_i| \leq \frac{\Delta}{2}\} \geq 1- 2\exp(-\Delta^2T/4), \qquad i=1,2.$$

Define the events $$A$$ and $$B$$ as the cases when $$\{\|\mu_1 - \hat{\mu_1}\| \leq \dfrac{\Delta}{2}\}$$ and $$\{\|\mu_2 - \hat{\mu_2}\| \leq \dfrac{\Delta}{2}\}$$ respectively. In this way, the event $$A \cap B$$ can be denoted by $$\{\max_{i=1,2} |\mu_i - \hat{\mu_i}| \leq \dfrac{\Delta}{2}\}$$. By using the union bound: $$\Pr(A\cap B)\geq 1-\Pr(A^c) -\Pr(B^c)$$ we get:

$$\Pr\[\max_{i=1,2}\{|\mu_i-\hat\mu_i|\}<\frac{\Delta}{2}\]\geq 1-4\exp( -\Delta^2T/4).$$

Observe that if $$\max_{i=1,2}\{|\mu_i-\hat\mu_i|\}<\frac{\Delta}{2}$$, then $$\hat \mu_1>\mu_1-\frac{\Delta}{2}>\mu_2-\frac{\Delta}{2}> \hat\mu_2$$. Hence, *ALG1* outputs the correct arm with probability at least $$1-4\exp( -\Delta^2T/4)$$.

**REMARK** If *ALG1* wants to succeed with probability $$1-\delta$$, $$T$$ should be at least $$\frac{4}{\Delta^2}\log(\frac{4}{\delta})$$.

In some scenarios, the objective may be maximizing the rewards collected instead of identifying the better arm. In these cases, we want to select one arm in each period to maximize the expected overall rewards $$\E\[\sum_{t=1}^Tr_t\],$$ where $$r_t$$ is the corresponding reward in period $$t$$, i.e., $$r_t$$ follows $$D_i$$ if selecting arm $$i$$ in period $$t$$, $$i=1,2$$. This problem of maximizing the collected revenue is equivalent to the following problem:

$$\min R_T,$$ 

where $$R_T$$ is the expected regret defined as $$R_T=T\max\{\mu_1,\mu_2\}-\E\[\sum_{t=1}^Tr_t\]$$.

Note that $$T\max\{\mu_1,\mu_2\}$$ is the maximal expected reward by playing the best arm all the time. The following result shows that the regret of *ALG1* is linear in $$T$$.

**Theorem 2:** $$R_T^{ALG1}=\frac{T}{2}\Delta$$.

**Proof:** Suppose $$\mu_1>\mu_2$$. Because *ALG1* play arm 2 in $$\frac{T}{2}$$ times. It follows that the regret is $$\frac{T}{2}\Delta$$.

As the regret of *ALG1* is of order $$\Omega (T)$$, it is a relatively bad regret. Thus, it is natural to think about othe algorithms. 

We consider another algorithm that first run *ALG1* for some time and then play the best arm identified by *ALG1* for the remaining time.

*Exploration and commit Algorithm*

Step 1: Call *ALG1* with parameter $$T_0$$, i.e., play each arm $$\frac{T_0}{2}$$ times.

Step 2: play the best arm returned by *ALG1* for the remaining $$T-T_0$$ periods.

**Theorem 3:** By choosing $$T_0=T^{2/3}\log^{1/3}(T)$$, the regret of exploration and commit algorithm is $$O(T^{2/3}\log^{1/3}(T))$$.

**Proof:** The regret incurred for the first $$T_0$$ periods is $$\frac{T_0}{2}\Delta$$. The regret incurred for the second step is 

$$\Pr\[\text{ALG1 fails}\](T-T_0)\Delta\leq 4\exp(-\frac{T_0\Delta^2}{4})T\Delta.$$
Hence,

$$R_T\lesssim T_0\Delta+4\exp(-\frac{T_0\Delta^2}{4})T\Delta.$$

Here, for two numbers $$a,b$$, $$a \lesssim b$$ means that $$a\leq bc$$ for some constant $c>0$. Denote

$$S=T_0\Delta+4\exp(-\frac{T_0\Delta^2}{4})T\Delta$$

We consider two cases:

(1) If $$\Delta^2\leq \frac{4\log(T)}{T_0}$$, then $$S\leq T\Delta+4T\Delta\lesssim T\sqrt{\frac{\log(T)}{T_0}}$$

(2) If $$\Delta^2> \frac{4\log(T)}{T_0}$$, then $$\exp(-\frac{T_0\Delta^2}{4})T<1$$, and thus $$S\leq (T_0+1)\Delta\leq T_0+1\lesssim T_0$$.
