---
layout: post
title: "Building Beauty: The Programmer’s Workshop Draft Pattern Language"
tags: building-beauty
---

# {{ page.title }}

A project pattern language “distills and describes the essence and character” of a specific building project (Neis et al., 1994). It describes the project’s details at multiple levels of scale, along with the connection to its wider context, with a sequence of statements that are clear enough to visualise, but leave enough ambiguity for the implementation to adapt to local conditions during an integrated process of design and construction.

This project language was written during [Building Beauty Online 2020 – 2021](/building-beauty) to guide the design and construction of my individual project. It is an attempt at re-balancing the small home workspace of a remote knowledge worker away from the monotony of a typical desk setup towards a more varied workspace akin to the workshop of a craftsman of previous generations. It is tailored to me as an individual, but guided by background research and several interviews with colleagues and fellow students.

I've meant to get this finished off, but until then here's where I got to for posterity.

<small>
  Some slides make reference to APL – [A Pattern Language](https://uk.bookshop.org/a/5361/9780195019193) – and a corresponding pattern number.
</small>

{% for i in (0..40) -%}
  {% assign padded = i | prepend: '00' | slice: -2, 2 %}

  <p id="card-{{ i }}">
    <img src="/images/posts/building-beauty/the-programmers-workshop-draft-{{ padded }}.jpg" />
  </p>
{% endfor -%}
