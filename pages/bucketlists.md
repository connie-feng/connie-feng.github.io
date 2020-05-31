---
layout: page
title: "Bucket Lists :scroll:"
permalink: "blog/bucketlists/"
---

<ul>
  {% for post in site.categories.bucketlists %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
