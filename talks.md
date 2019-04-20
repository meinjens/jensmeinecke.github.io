---
layout: page
title: Talks
bigimg: /assets/niagara_falls_light.jpg
---

<ul class="fa-ul">
{% assign talks = site.talks | sort: 'talk_end_date' | reverse %}
{% for talk in talks %}
  <li>
    <h3><i class="fa-li fa fa-graduation-cap"></i><a href="{{ talk.url }}">{{ talk.title }}</a></h3>
    {% if talk.talk_end_date %}
      <i class="fa fa-calendar"></i> {{ talk.talk_start_date | date: "%m.%Y" }}
      - {{ talk.talk_end_date | date: "%m.%Y" }}
    {% else %}
      <i class="fa fa-calendar"></i> {{ talk.talk_start_date | date: "%m.%Y" }}
    {% endif %}
          &nbsp;
          <i class="fa fa-map-marker"></i> {{ talk.talk_location }}
  </li>
{% endfor %}
</ul>
