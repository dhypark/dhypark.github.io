---
layout: page
title: projects
permalink: /projects/
description: A growing collection of your cool projects.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

<div class="projects">
{% if site.enable_project_categories %}
  {% for category in site.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {% assign categorized_projects = site.projects | where: "category", category %}
  <div class="container">
    <div class="row">
      {% for project in categorized_projects %}
      {% include projects.liquid %}
      {% endfor %}
    </div>
  </div>
  {% endfor %}
{% else %}
  <div class="container">
    <div class="row">
      {% for project in site.projects %}
      {% include projects.liquid %}
      {% endfor %}
    </div>
  </div>
{% endif %}
</div>
