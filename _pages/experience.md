---
layout: page
permalink: /experience/
title: Experience
nav: true
nav_order: 2
description: Professional experience in performance engineering, cloud systems, and AI infrastructure.
experience:
  - year: "2026"
    dates: "Jan 2026 – Present"
    role: "Performance Engineer"
    org: "NetApp"
    url: "https://www.netapp.com/"
    location: "San Jose, CA"
    highlights: |
      - Optimizing performance of AIDE (AI Data Engine), a distributed platform for ingesting, cataloging, and serving enterprise storage data for AI workloads.
  - year: "2024"
    dates: "May 2024 – Jan 2026"
    role: "Performance and Capacity Engineer"
    org: "Meta Platforms, Inc."
    url: "https://about.meta.com/"
    location: "Menlo Park, CA"
    highlights: |
      - Optimized rack power budgets for multiple AI-inference hardware programs → **$100M/year** in data-center OpEx savings and a standardized budget-optimization framework across Meta's AI infrastructure hardware programs.
      - Drove cross-functional work to raise the power limit of GPUs used by recommendation services → **7% reduction** in GPU capacity required with no increase in power budget (**$400k/year** benefit).
      - Delivered power budget for flash-storage racks providing **7.3 EB** of storage to support GenAI training.
      - Delivered power budget for flash-storage racks providing **9.9 EB** of storage to support MySQL and other services.
      - Redesigned the Power Sufficiency Simulator pipeline, increasing input accuracy and reducing Thrift service dependencies by **77%**.
      - Created a machine-level power-estimation methodology for power-capped machines, improving power-capping efficiency by **11%** or reducing overage risk by **0.15%**, depending on the scenario.
      - Developed a technique to estimate power at the power-device level from host-level metrics, reaching **99%+ accuracy** and eliminating **0.9%–6%** estimation error across power-device types.
      - Improved idle-host power-usage estimation accuracy by up to **31%**, strengthening rack-level budget planning.
  - year: "2022"
    dates: "May 2022 – Aug 2022"
    role: "Research Intern"
    org: "Cloud Operations Research (CORE), Microsoft Research"
    url: "https://www.microsoft.com/en-us/research/"
    location: "Redmond, WA"
    highlights: |
      - Designed Kerveros, a novel Azure admission-control system → **95%+ utilization** at **99.9%+ availability** in production; deployed in Azure and published at OSDI 2023.
  - year: "2021"
    dates: "May 2021 – Aug 2021"
    role: "Research Intern"
    org: "Gray Systems Lab (GSL), Microsoft"
    url: "https://www.microsoft.com/en-us/research/"
    location: "Redmond, WA"
    highlights: |
      - Built realistic Azure HDInsight benchmarks by reconstructing Spark workloads from query traces; generated privacy-preserving synthetic datasets.
  - year: "2018"
    dates: "Aug 2018 – May 2024"
    role: "Graduate Research & Teaching Assistant"
    org: "Pennsylvania State University"
    url: "https://www.psu.edu/"
    location: "University Park, PA"
    highlights: |
      - Research on cloud-systems evaluation methodology (publications at EuroSys 2024 and 2021).
      - Teaching assistant for multiple undergraduate courses.
  - year: "2017"
    dates: "Oct 2017 – Jul 2018"
    role: "Junior Software Engineer"
    org: "Reve Systems"
    location: "Dhaka, Bangladesh"
    highlights: |
      - Prototyped a machine-translation system supporting Bangla and 25 additional languages.
      - Built a Bangla NLP platform prototype (machine translator, spell checker, and more).
---

{% assign t = site.data.timeline %}
{% for job in page.experience %}

<div style="{{ t.grid }}">
  <div style="{{ t.year }}">{{ job.year }}</div>
  <div style="{% if forloop.last %}{{ t.rail_last }}{% else %}{{ t.rail }}{% endif %}">
    <span style="{{ t.dot }}"></span>
    <div style="{{ t.date }}">{{ job.dates }}</div>
    <div style="{{ t.title }}">{{ job.role }} — {% if job.url %}<a href="{{ job.url }}">{{ job.org }}</a>{% else %}{{ job.org }}{% endif %}</div>
    <div style="{{ t.loc }}">{{ job.location }}</div>
    {{ job.highlights | markdownify }}
  </div>
</div>
{% endfor %}
