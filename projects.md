---
layout: page
title: Projekte
subtitle: Kleine und große Projekte
bigimg: /assets/myway.jpg
---

<ul class="fa-ul">
{% assign projects = site.projects | sort: 'project_end_date' | reverse %}
{% for project in projects %}
  {% if project.project_type == "implementation" %}
    {% assign icon = 'fa-laptop' %}
  {% else %}
    {% assign icon = 'fa-graduation-cap' %}
  {% endif %}

  <li>
    <h3><i class="fa-li fa {{ icon }}"></i><a href="{{ project.url }}">{{ project.title }}</a></h3>
    {% if project.project_end_date %}
      <i class="fa fa-calendar"></i> {{ project.project_start_date | date: "%m.%Y" }}
      - {{ project.project_end_date | date: "%m.%Y" }}
    {% else %}
      <i class="fa fa-calendar"></i> {{ project.project_start_date | date: "%m.%Y" }}
    {% endif %}
          &nbsp;
          <i class="fa fa-map-marker"></i> {{ project.project_location }}
  </li>
{% endfor %}
</ul>