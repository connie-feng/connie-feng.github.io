---
layout: page
title: "Recipes :rice:"
permalink: "blog/recipes/"
---

<ul>
  {% for post in site.categories.recipes %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
