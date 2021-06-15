---
layout: post
title: "Book Notes – Nature of Order Book 1: The Phenomenon of Life"
tags: building-beauty
---

# {{ page.title }}

Currently only my hand-written notes. One day I'll type these up…

[Book 2](/2021/06/15/book-notes-nature-of-order-book-2) – The Process of Creating Life &rarr;

{% for i in (1..26) -%}
  {% assign padded = i | prepend: '00' | slice: -2, 2 %}

  {% if i == 4 or i == 6 or i == 10 %}
  <p id="card-{{ i }}" class="minor-note">
    Card {{ i }} intentionally left blank
  </p>
  {% else %}
  <p id="card-{{ i }}">
    <img src="/images/posts/building-beauty/book-1-{{ padded }}.jpg" />
  </p>
  {% endif %}
{% endfor -%}
