---
layout: archive
permalink: /research/
author_profile: true
---

<!-- Google Scholar Link -->
{% if author.googlescholar %}
  <p>You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u></p>
{% endif %}

<!-- Include Base Path -->
{% include base_path %}

<!-- Display Publications by Category -->
{% for category in site.publication_category %}
  <h2 class="publication-category-title">{{ category[1].title }}</h2>
  {% assign category_key = category[0] %}
  {% assign posts_in_category = site.research | where: "category", category_key %}
  {% for post in posts_in_category reversed %}
    {% include archive-single.html post=post %}
  {% endfor %}
{% endfor %}

<!-- JavaScript for Abstract Toggle -->
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
