---
layout: archive
title: "Applied Research"
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

## Education

**University of Illinois Urbana-Champaign** — Urbana, IL, USA
*Ph.D., 2021*

- **Thesis:** Choice modeling and recommendation optimization in presence of context effects — [[Link]](https://www.ideals.illinois.edu/items/121110)
- **Advisor:** Professor Xin Chen — [[Link]](https://www.isye.gatech.edu/users/xin-chen)
- **Honors / Awards:** (i) Received full funding from the Walmart Labs Personalization team based on direct applicability of thesis research. (ii) Won the Hansen Fellowship, awarded to bright graduate students.

---

## Selected Applied Research

*Based on A/B tests and product launches.*

**Role legend:** [L] Lead Author · [CL] Co-Lead Author · [CA] Corresponding Author · [C] Contributing Author

### Agentic Solutions

- Perspectives on agentic RecSys — under review at [ACM ToRS](https://arxiv.org/pdf/2507.02097) — **[L]**
- Reducing output variance in multi-agentic evaluation — [NeurIPS25-W](https://openreview.net/pdf?id=uSijBMsVqW) — **[L]**
- Multi-agentic evaluation through crowd-sourcing agents — [NeurIPS25-W](https://arxiv.org/pdf/2511.03051) — **[C]**
- Explanation generation for RecSys — [ICML25-W](https://arxiv.org/pdf/2506.17765) — **[CL]**

### Retrieval, RAG, and Language/Vision Generation (workshops)

- Text generation with user implicit feedback — [NeurIPS25-W](https://arxiv.org/pdf/2510.01523v1) — **[CA, CL]**
- Personalized recommendation with agentic RAG — [SIGIR25-W](https://arxiv.org/pdf/2506.21931) — **[L]**
- Geometric RAG for layout design — [SIGIR25-W](https://arxiv.org/pdf/2506.21934) — **[L]**
- Abstractive keyword extraction — [IEEE BigData23](https://arxiv.org/pdf/2312.00909) — **[L]**

### Algorithms

- User Inference and Combinatorial Assortment Optimization — under review at [MSOM](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3747354); also covered in my [Ph.D. Thesis](https://www.ideals.illinois.edu/items/121110) — **[L]**

### ML/DL for Industrial IR / RecSys (workshops)

- LLM-based embeddings for recommendation — [ICML23-W](https://openreview.net/pdf?id=bStpLVqv1H) — **[L]**
- Deals recommendation based on prospect theory — [IEEE BigData22](https://ieeexplore.ieee.org/abstract/document/10020542) — **[L]**
- GNN-based similar item recommendation — [ICDM23](https://arxiv.org/pdf/2310.17732) — **[C]**
- Seller-side fairness in online marketplaces — [NeurIPS23-W](https://arxiv.org/pdf/2312.03253) — **[CA]**

---

## Tutorials & Talks

- Tutorial on Agentic RecSys at [ACM RecSys25](https://dl.acm.org/doi/epdf/10.1145/3705328.3748008) and [SIGIR26](https://sigir2026.org/en-AU/pages/program/accepted-tutorials)
- Invited talk on Modern Topics in Recommender Systems at [TU Wien](https://recsys-lab.at/rsss2025/recordings/)

---

## US Patents

1. [Document Theme Extraction](https://patents.google.com/patent/US20250245449A1)
2. [Similar Item Recommendation](https://patents.google.com/patent/US20250245479A1)
3. [User Representations](https://patents.google.com/patent/US20240242069A1)
4. [Hybrid Optimization](https://patents.google.com/patent/US20240256874A1/)

*Four additional patents pending.*
