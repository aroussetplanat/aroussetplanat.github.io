---
layout: archive
permalink: /research/
title: Research
---

<h1>Research</h1>

{% for post in site.research %}
  {% include archive-single.html post=post %}
{% endfor %}
