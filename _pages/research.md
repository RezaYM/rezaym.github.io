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


## Selected Applied Research

*Based on A/B tests and product launches.*

**Role legend:** [L] Lead Author · [CL] Co-Lead Author · [CA] Corresponding Author · [C] Contributing Author

### Agentic Solutions

- Perspectives on agentic RecSys, under review at [ACM ToRS](https://arxiv.org/pdf/2507.02097), **[L]**
- Reducing output variance in multi-agentic evaluation, [NeurIPS25-W](https://openreview.net/pdf?id=uSijBMsVqW), **[L]**
- Multi-agentic evaluation through crowd-sourcing agents, [NeurIPS25-W](https://arxiv.org/pdf/2511.03051), **[C]**
- Explanation generation for RecSys, [ICML25-W](https://arxiv.org/pdf/2506.17765), **[CL]**

### Retrieval, RAG, and Language/Vision Generation

- Text generation with user implicit feedback, [NeurIPS25-W](https://arxiv.org/pdf/2510.01523v1), **[CA, CL]**
- Personalized recommendation with agentic RAG, [SIGIR25-W](https://arxiv.org/pdf/2506.21931), **[L]**
- Geometric RAG for layout design, [SIGIR25-W](https://arxiv.org/pdf/2506.21934), **[C]**
- Abstractive keyword extraction, [IEEE BigData23](https://arxiv.org/pdf/2312.00909), **[L]**

### Algorithms

- User Inference and Combinatorial Assortment Optimization, under review at [MSOM](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3747354); also covered in my [Ph.D. Thesis](https://www.ideals.illinois.edu/items/121110), **[L]**

### ML/DL for Industrial IR / RecSys (workshops)

- LLM-based embeddings for recommendation, [ICML23-W](https://openreview.net/pdf?id=bStpLVqv1H), **[L]**
- Deals recommendation based on prospect theory, [IEEE BigData22](https://ieeexplore.ieee.org/abstract/document/10020542), **[L]**
- GNN-based similar item recommendation, [ICDM23](https://arxiv.org/pdf/2310.17732), **[C]**
- Seller-side fairness in online marketplaces, [NeurIPS23-W](https://arxiv.org/pdf/2312.03253), **[CA]**

---

## Tutorials & Talks

- Aug 25: Invited talk on Modern Topics in Recommender Systems at [TU Wien](https://recsys-lab.at/rsss2025/recordings/), Vienna, Austria
- Sep 25: Tutorial on Agentic RecSys at [ACM RecSys25](https://dl.acm.org/doi/epdf/10.1145/3705328.3748008), 
- Aril 26: Invited talk on Agentic Retail, [Richard A. Chaifetz School of Business, SLU](https://www.slu.edu/business/index.php)
- July 26: Tutorial on Production Grade Agentic Recommender Systems [SIGIR26](https://sigir2026.org/en-AU/pages/program/accepted-tutorials)


---

<!-- ============================================================
     Talks map — self-contained, no API key required.
     Drop this whole block into your Markdown page, or save it as
     talks-map.html and embed it with an <iframe>. See notes below.
     ============================================================ -->

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<div id="talks-map-wrapper">
  <div id="talks-map"></div>
  <div class="talks-legend">
    <span><i class="dot past"></i> Past</span>
    <span><i class="dot upcoming"></i> Upcoming</span>
  </div>
</div>

<style>
  #talks-map-wrapper {
    position: relative;
    max-width: 820px;
    margin: 1.5rem auto;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
  }
  #talks-map {
    height: 460px;
    width: 100%;
    border: 1px solid #e2e2e2;
    border-radius: 10px;
    z-index: 0;
  }
  .talks-legend {
    position: absolute;
    bottom: 14px;
    right: 14px;
    background: rgba(255, 255, 255, 0.92);
    border: 1px solid #e2e2e2;
    border-radius: 8px;
    padding: 7px 11px;
    font-size: 12.5px;
    color: #333;
    display: flex;
    gap: 14px;
    z-index: 500;
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.08);
  }
  .talks-legend .dot {
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    margin-right: 4px;
    vertical-align: middle;
  }
  .talks-legend .dot.past { background: #2c5f8a; }
  .talks-legend .dot.upcoming { background: #c0631f; }

  .talk-popup { font-size: 13px; line-height: 1.45; }
  .talk-popup .venue { font-weight: 600; color: #1a1a1a; }
  .talk-popup .place { color: #555; }
  .talk-popup .date { color: #888; font-size: 12px; }

  .talk-pin {
    width: 26px;
    height: 26px;
    border-radius: 50% 50% 50% 0;
    transform: rotate(-45deg);
    border: 2px solid #fff;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
    display: flex;
    align-items: center;
    justify-content: center;
  }
  .talk-pin span {
    transform: rotate(45deg);
    color: #fff;
    font-size: 12px;
    font-weight: 700;
  }
  .talk-pin.past { background: #2c5f8a; }
  .talk-pin.upcoming { background: #c0631f; }
</style>

<script>
  (function () {
    var talks = [
      { n: 1, venue: "RecSys 2025", place: "Prague, Czech Republic", date: "Sep 2025", lat: 50.0755, lng: 14.4378, status: "past" },
      { n: 2, venue: "TU Wien", place: "Vienna, Austria", date: "Aug 2025", lat: 48.2082, lng: 16.3738, status: "past" },
      { n: 3, venue: "Richard A. Chaifetz School of Business", place: "St. Louis, MO, USA", date: "Apr 2026", lat: 38.6270, lng: -90.1994, status: "past" },
      { n: 4, venue: "SIGIR 2026", place: "Melbourne, Australia", date: "Jul 2026", lat: -37.8136, lng: 144.9631, status: "upcoming" }
    ];

    var map = L.map("talks-map", { scrollWheelZoom: false, worldCopyJump: true });

    L.tileLayer("https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png", {
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors &copy; <a href="https://carto.com/attributions">CARTO</a>',
      maxZoom: 19
    }).addTo(map);

    var bounds = [];
    talks.forEach(function (t) {
      var icon = L.divIcon({
        className: "",
        html: '<div class="talk-pin ' + t.status + '"><span>' + t.n + "</span></div>",
        iconSize: [26, 26],
        iconAnchor: [13, 26],
        popupAnchor: [0, -26]
      });
      L.marker([t.lat, t.lng], { icon: icon })
        .addTo(map)
        .bindPopup(
          '<div class="talk-popup"><div class="venue">' + t.venue +
          '</div><div class="place">' + t.place +
          '</div><div class="date">' + t.date + "</div></div>"
        );
      bounds.push([t.lat, t.lng]);
    });

    map.fitBounds(bounds, { padding: [50, 50] });
  })();
</script>

## US Patents

1. [Document Theme Extraction](https://patents.google.com/patent/US20250245449A1)
2. [Similar Item Recommendation](https://patents.google.com/patent/US20250245479A1)
3. [User Representations](https://patents.google.com/patent/US20240242069A1)
4. [Hybrid Optimization](https://patents.google.com/patent/US20240256874A1/)

*Four additional patents pending.*


## PhD Thesis

**University of Illinois Urbana-Champaign** — Urbana, IL, USA
*Ph.D., 2021*

- **Thesis:** Choice modeling and recommendation optimization in presence of context effects, [[Link]](https://www.ideals.illinois.edu/items/121110)
- **Advisor:** Professor Xin Chen, [[Link]](https://www.isye.gatech.edu/users/xin-chen)
- **Honors / Awards:** (i) Received full funding from the Walmart Labs Personalization team based on direct applicability of thesis research. (ii) Won the Hansen Fellowship, awarded to bright graduate students.

