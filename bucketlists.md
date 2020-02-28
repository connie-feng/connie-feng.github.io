---
layout: page
title: "Bucket Lists :scroll:"
permalink: /bucketlists/
---

<ul>
  {% for post in site.categories.bucketlists %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}" target="_blank">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
