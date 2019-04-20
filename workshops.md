---
layout: page
title: Workshops
bigimg: /assets/kaiserschmarn.jpg
---

<ul class="fa-ul">
{% assign workshops = site.workshops | sort: 'workshop_end_date' | reverse %}
{% for workshop in workshops %}
  <li>
    <h3><i class="fa-li fa fa-graduation-cap"></i><a href="{{ workshop.url }}">{{ workshop.title }}</a></h3>
    {% if workshop.workshop_end_date %}
      <i class="fa fa-calendar"></i> {{ workshop.workshop_start_date | date: "%m.%Y" }}
      - {{ workshop.workshop_end_date | date: "%m.%Y" }}
    {% else %}
      <i class="fa fa-calendar"></i> {{ workshop.workshop_start_date | date: "%m.%Y" }}
    {% endif %}
          &nbsp;
          <i class="fa fa-map-marker"></i> {{ workshop.workshop_location }}
  </li>
{% endfor %}
</ul>
