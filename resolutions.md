---
layout: page
title: Resolutions
permalink: /resolutions/
---

<ul>
  {% for post in site.categories.resolutions %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}" target="_blank">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
