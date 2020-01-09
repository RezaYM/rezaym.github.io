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

