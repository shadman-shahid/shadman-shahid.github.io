---
layout: page
permalink: /research/
title: Research
description: 
years: [2022]
nav: true
nav_order: 2
---
A list of my publications are provided here. Google scholar link is provided [here](https://scholar.google.com/citations?hl=en&user=Yhv2nC8AAAAJ). I will keep updating the list over time. These are only the articles that have been published in journals or conferences. Un-published works are listed under __"Projects"__.
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f {{ site.scholar.bibliography }} -q @*[year={{y}}]* %}
{% endfor %}

</div>
