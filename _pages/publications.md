---
layout: page
permalink: /publications/
title: Publications
description: List of all <em>accepted</em> publications
years: [2021, 2022]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->

The following page is generated manually, an up-to-date list is available on <a href="https://scholar.google.com/citations?hl=en&user=QWFKVW8AAAAJ&view_op=list_works&sortby=pubdate">Google Scholar</a>.

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
