---
layout: page
title: Talks
bigimg: /assets/niagara_falls_light.jpg
permalink: /talks
---

<ul class="fa-ul">
{% assign talks = site.talks | sort: 'talk_end_date' | reverse %}
{% for talk in talks %}
  <li>
    <h3><i class="fa-li fa fa-graduation-cap"></i><a href="{{ talk.url }}">{{ talk.title }}</a></h3>
      <i class="fa fa-calendar"></i> {{ talk.talk_next_date }}
      &nbsp;
      <i class="fa fa-map-marker"></i> {{ talk.talk_location }}
  </li>
{% endfor %}
</ul>
