---
title: Home
layout: default
heading-meta: About Me KEKW
heading: Who Am I KEKW
---

Some page content here...

<ul>
  {% assign mypages = site.pages %}
    {% for page in mypages %}
    <li><a href="{{ page.url | absolute_url }}">{{ page.title }}</a></li>
    {% endfor %}
</ul>

<ul>
    {% for link in site.data.navigation %}
    <li><a href="{{ link.url | absolute_url }}">{{ link.title }}</a></li>
    {% endfor %}
</ul>