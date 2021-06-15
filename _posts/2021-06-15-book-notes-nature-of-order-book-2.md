---
layout: post
title: "Book Notes – Nature of Order Book 2: The Process of Creating Life"
tags: building-beauty
---

# {{ page.title }}

Currently only my hand-written notes. One day I'll type these up…

[&larr; Book 1](/2021/06/09/book-notes-nature-of-order-book-1) – The Phenomenon of Life

<!--
[Book 3](/2021/06/??/book-notes-nature-of-order-book-3) – A Vision of a Living World &rarr;
-->

{% for i in (1..26) -%}
  {% assign padded = i | prepend: '00' | slice: -2, 2 %}

  <p id="card-{{ i }}">
    <img src="/images/posts/building-beauty/book-2-{{ padded }}.jpg" />
  </p>
{% endfor -%}
