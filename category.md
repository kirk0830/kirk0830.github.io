---
layout: default
title: Category
---
<h1>Category</h1>

<ul>
  {% for category in site.categories %}
    <li>
      <h2><a href="{{ category.url }}">{{ category.name }}</a></h2>
      <p>{{ category.content | markdownify }}</p>
    </li>
  {% endfor %}
</ul>