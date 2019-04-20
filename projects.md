---
layout: page
title: Projekte
bigimg: /assets/myway.jpg
permalink: /projects
---

<ul class="fa-ul">
{% assign projects = site.projects | sort: 'project_end_date' | reverse %}
{% for project in projects %}
  {% if project.project_type == "implementation" %}
    {% assign icon = 'fa-laptop' %}
  {% elsif project.project_type == "consulting" %}
    {% assign icon = 'fa-building' %}
  {% elsif project.project_type == "experiment" %}
    {% assign icon = 'fa-flask' %}
  {% elsif project.project_type == "workshop" %}
    {% assign icon = 'fa-graduation-cap' %}
  {% elsif project.project_type == "talk" %}
    {% assign icon = 'fa-quote-right' %}
  {% else %}
    {% assign icon = 'fa-desktop' %}
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

<ul class="fa-ul legend">
  <li><i class="fa-li fa fa-laptop"></i> Implementierung</li>
  <li><i class="fa-li fa fa-building"></i> Beratung</li>
  <li><i class="fa-li fa fa-flask"></i> Experiment</li>
  <li><i class="fa-li fa fa-graduation-cap"></i> Workshop</li>
  <li><i class="fa-li fa fa-quote-right"></i> Talk</li>
  <li><i class="fa-li fa fa-desktop"></i> Sonstige</li>
</ul>