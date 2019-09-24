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

# Papers:
* Working Paper: Revenue Management in Prsenece of Context Effects
* 
