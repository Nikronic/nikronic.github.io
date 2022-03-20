---
title: Home
layout: default
heading-meta: About Me KEKW
heading: Who Am I KEKW
---

Some page content here...

{% assign counter = 0 %}
{% for i in (0..10) %}
    {% if counter >= 4 %}
        {% break %}
    {% endif %}    
    {% if i > 0 %}
        {% assign counter = counter | plus: 1 %}
    {% endif %}
{% endfor %}
{{counter}}<br>
{{i}}