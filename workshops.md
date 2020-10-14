---
layout: page
title: Workshops
bigimg: /assets/kaiserschmarn.jpg
permalink: /workshops
---

<ul class="fa-ul">
{% assign workshops = site.workshops | sort: 'date' | reverse %}
{% for workshop in workshops %}
  <li>
    <h3>
    <i class="fa-li fa fa-graduation-cap"></i><a href="{{ workshop.url }}">{{ workshop.title }}</a></h3>
      <i class="fa fa-calendar"></i> {{ workshop.next_date }}
      &nbsp;
      <i class="fa fa-map-marker"></i> {{ workshop.location }}
  </li>
{% endfor %}
</ul>
