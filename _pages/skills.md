---
layout: page
permalink: /skills/
title: Skills
nav: true
nav_order: 4
description: Technical skills across systems, cloud, and tooling.
skills:
  - name: "Specialized Areas"
    items: ["Distributed Systems", "Systems Benchmarking", "Power Budget Optimization", "Performance Analysis"]
  - name: "Languages"
    items: ["Python", "Java", "C++", "Scala", "R"]
  - name: "Frameworks & Tools"
    items: ["Pandas", "Apache Spark", "Docker", "Kubernetes", "Git"]
  - name: "Cloud Platforms"
    items: ["AWS", "Azure"]
  - name: "Web & DevOps"
    items: ["Nginx", "Varnish", "Memcached"]
  - name: "Databases"
    items: ["MySQL", "PostgreSQL", "Presto"]
  - name: "Scripting"
    items: ["Bash"]
---

{% assign t = site.data.timeline %}

<div style="{{ t.skills_wrap }}">
{% for cat in page.skills %}
<div style="{% if forloop.last %}{{ t.rail_last }}{% else %}{{ t.rail }}{% endif %}">
<span style="{{ t.dot }}"></span>
<div style="{{ t.skill_title }}">{{ cat.name }}</div>
<div>
{% for item in cat.items %}<span style="{{ t.pill }}">{{ item }}</span>{% endfor %}
</div>
</div>
{% endfor %}
</div>
