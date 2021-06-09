---
layout: post
title: "Book Notes – Nature of Order Book 1: The Phenomenon of Life"
---

# {{ page.title }}

Currently only my hand-written notes. One day I'll type these up…

{% for i in (1..26) -%}
  {% assign padded = i | prepend: '00' | slice: -2, 2 %}

  {% if i == 4 %}
    {% continue %}
  {% elsif i == 6 %}
    {% continue %}
  {% elsif i == 10 %}
    {% continue %}
  {% else %}
  <p id="{{ i }}">
    <img src="/images/posts/building-beauty/book-1-{{ padded }}.jpg" />
  </p>
  {% endif %}
{% endfor -%}
