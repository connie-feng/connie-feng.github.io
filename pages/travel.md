---
layout: page
title: "Travel"
permalink: "blog/travel/"
---

<h3>Packing Lists</h3>
{% include list-posts entries='1000' offset='0' category='packing' %}

<h3>Costa Rica</h3>
{% include list-posts entries='1000' offset='0' category='costa_rica' %}

<h3>Hawaii</h3>
{% include list-posts entries='1000' offset='0' category='hawaii' %}

<h3>Japan</h3>
{% include list-posts entries='1000' offset='0' category='japan' %}

<!-- <h3>London</h3>
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
</ul> -->

<h3>India</h3>
{% include list-posts entries='1000' offset='0' category='india' %}
