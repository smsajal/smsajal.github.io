---
layout: page
permalink: /education/
title: Education
nav: true
nav_order: 3
description: Academic background in Computer Science and Engineering.
education:
  - year: "2018"
    dates: "Aug 2018 – May 2024"
    role: "Ph.D., Computer Science and Engineering"
    org: "Pennsylvania State University"
    url: "https://www.psu.edu/"
    location: "University Park, PA"
    highlights: |
      - Dissertation: _Improving the Fidelity of Trace-Driven Experiments in Cloud Computing Systems._
      - Advisors: Prof. Timothy Zhu and Prof. Bhuvan Urgaonkar.
      - Published at OSDI, EuroSys (×2), and ACM TOCS.
  - year: "2013"
    dates: "Feb 2013 – Sep 2017"
    role: "B.Sc., Computer Science and Engineering"
    org: "Bangladesh University of Engineering and Technology (BUET)"
    url: "https://www.buet.ac.bd/"
    location: "Dhaka, Bangladesh"
    highlights: |
      - Technical Scholarship recipient.
---

{% assign t = site.data.timeline %}
{% for edu in page.education %}
<div style="{{ t.grid }}">
<div style="{{ t.year }}">{{ edu.year }}</div>
<div style="{% if forloop.last %}{{ t.rail_last }}{% else %}{{ t.rail }}{% endif %}">
<span style="{{ t.dot }}"></span>
<div style="{{ t.date }}">{{ edu.dates }}</div>
<div style="{{ t.title }}">{{ edu.role }} — {% if edu.url %}<a href="{{ edu.url }}">{{ edu.org }}</a>{% else %}{{ edu.org }}{% endif %}</div>
<div style="{{ t.loc }}">{{ edu.location }}</div>
{{ edu.highlights | markdownify }}
</div>
</div>
{% endfor %}
