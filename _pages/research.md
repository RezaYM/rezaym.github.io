---
layout: archive
title: "Research"
permalink: /Research/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.research reversed %}
  {% include archive-single.html %}
{% endfor %}

### Interests:
* Recommendation Systems,
* Pricing and Revenue Management,
* Online Learning and Multi-Armed Bandit Settings,
* Application of Deep Learning in Revenue Management Settings,
* Optimization of Deep Neural Nets.

### Recommendation Systems:
* R. Y. Maragheh, X. Chen, J. M. Davis, Jason Cho, Sushant Kumar, *Choice Modeling and Assortment Optimization inthe Presence of Context Effects*, Under submission to Management Science.
* R. Y. Maragheh, X. Chen, Luyi Ma, Chuanwei Ruan, Jason Cho, Sushant Kumar, *Set Dependent Ranking Model: By Considering Substitution Patterns and Contextual Effects*, Under Submission to SIGIR2020.
* R. Y. Maragheh, [*Assortment Optimization/Competition under Context Effects*](https://www.abstractsonline.com/pp8/#!/9022/session/2572),  Session at Informs 2020.
* R. Y. Maragheh, A. Chronopoulou, J. Davis, [*A Customer Choice Model for Estimating the Halo Effect*](https://arxiv.org/abs/1805.01603), Presented at 2017 Informs Annual Meeting, Houston, Texas, 2017.

### Machine learning and Deep Learning
* R.Y. Maragheh, Easing Optimization of Ackley Function with overparameterization Using Neural Nets, Working Paper.

### Policy Design
* M. Modarres, M. Feizabadi, and R. Y. Maragheh, [*A Dynamic Programming Approach forInvestment Problem with Stochastic
Number of Investment Chances*](https://www.researchgate.net/publication/260144937_A_dynamic_programming_approach_for_investment_problem_with_stochastic_number_of_investment_chances), in Tenth International Industrial Engineering Conference, Tehran, Iran, 2014.
* *Stackelberg Game Formulation and Equilibrium of The Interaction Between Shareholders and Employees on Issuing Employee Stock Options*, Master Thesis. [Abstract](https://www.researchgate.net/publication/279285970_Stackelberg_Game_Formulation_and_Equilibrium_of_The_Interaction_Between_Shareholders_and_Employees_on_Issuing_Employee_Stock_Options)
