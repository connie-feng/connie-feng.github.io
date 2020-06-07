---
layout: page
title: "Software Engineering :computer:"
permalink: "blog/software_engineering/"
---

<ul>
  {% for post in site.categories.tech %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
