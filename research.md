---
layout: archive
permalink: /research/
author_profile: true
---

<h1>Research</h1>

{% for post in site.research %}
  {% include archive-single.html post=post %}
{% endfor %}
