---
layout: page
title: Projects
permalink: /projects/
description: Some of the projects and other research endeavors that I have worked on.  
nav: true
nav_order: 3
display_categories: [academic, work]
horizontal: false
---

For now, the projects are not described. Only the cards are shown. Overtime I will gradually, populate the contents of each of the projects. 

*These projects include research works that have not been published (yet). Published works are listed under __Research__*

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  
  {% if category=='work' -%}
  <br>
  The following projects are the ones I worked on as a part of my job at ACI Limited. The list is not exhaustive, as I have omitted many of the aspects of individual projects, due to confidentiality. However, I have tried to be as descriptive as possible. Just like the other projects, I will keep updating these over time.  
  {%- endif -%}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
