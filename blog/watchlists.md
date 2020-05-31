---
layout: page
title: "Watch Lists :tv:"
permalink: "blog/watchlists/"
---

<ul>
  {% for post in site.categories.watchlists %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}" target="_blank">
          {{ post.title }}
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
