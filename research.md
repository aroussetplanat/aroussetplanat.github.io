---
layout: archive
permalink: /research/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for category in site.publication_category %}
  <h2 class="publication-category-title">{{ category[1].title }}</h2>
  {% assign category_key = category[0] %}
  {% assign posts_in_category = site.publications | where: "category", category_key %}
  {% for post in posts_in_category reversed %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}


<script>
function toggleAbstract(slug) {
  var abstractDiv = document.getElementById('abstract-' + slug);
  var button = document.querySelector('a[onclick="toggleAbstract(\'' + slug + '\'); return false;"]');
  if (abstractDiv.style.display === 'none') {
    abstractDiv.style.display = 'block';
    button.setAttribute('aria-expanded', 'true');
  } else {
    abstractDiv.style.display = 'none';
    button.setAttribute('aria-expanded', 'false');
  }
}
</script>
