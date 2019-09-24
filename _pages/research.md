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

# Interests:
* Pricing and Revenue Management
* Online Learning and Multi-Armed Bandit Problems
* Application of Deep Learning in Revenue Management Settings

# Papers and Conferences:
* R. Y. Maragheh, X. Chen, A. Chronopoulou, J. M. Davis, *Revenue Management in Prsenece of Context Effects*, Under submission to Operations Rsearch.
* R. Y. Maragheh, A. Chronopoulou, J. Davis, [*A Customer Choice Model for Estimating the Halo Effect*](https://arxiv.org/abs/1805.01603), Presented at 2017 Informs Annual Meeting, Houston, Texas, 2017.
* R.Y. Maragheh, Easing Optimization of Ackley Function with overparameterization Using Neural Nets, Working Paper.
* M. Modarres, M. Feizabadi, and R. Y. Maragheh, [*A Dynamic Programming Approach forInvestment Problem with Stochastic
Number of Investment Chances*](https://www.researchgate.net/publication/260144937_A_dynamic_programming_approach_for_investment_problem_with_stochastic_number_of_investment_chances), in Tenth International Industrial Engineering Conference, Tehran, Iran, 2014.
* *Stackelberg Game Formulation and Equilibrium of The Interaction Between Shareholders and Employees on Issuing Employee Stock Options*, Master Thesis. [Abstract](https://www.researchgate.net/publication/279285970_Stackelberg_Game_Formulation_and_Equilibrium_of_The_Interaction_Between_Shareholders_and_Employees_on_Issuing_Employee_Stock_Options)
