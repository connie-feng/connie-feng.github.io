---
layout: page
title: "Travel :airplane:"
permalink: /travel/
---

<h3>Japan</h3>
<ul>
  {% for post in site.categories.japan %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}" target="_blank">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>

<h3>London</h3>
<ul>
  {% for post in site.categories.london %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}" target="_blank">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>

<h3>India</h3>
<ul>
  {% for post in site.categories.india %}
    {% if post.url %}
      <li>
        <a href="{{ post.url }}" target="_blank">
          {{ post.title }} [{{ post.date | date: '%B %d, %Y' }}]
        </a>
      </li>
    {% endif %}
  {% endfor %}
</ul>
