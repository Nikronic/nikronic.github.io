---
title: Home
layout: default
heading-meta: About Me KEKW
heading: Who Am I KEKW
---

Some page content here...

<ul>
    {% for link in site.data.navigation %}
    <li>
        <a href="{{ link.url | absolute_url }}">{{ link.title }}</a>
        <img src="{{ link.image | absolute_url }}">
    </li>
    {% endfor %}
    
</ul>