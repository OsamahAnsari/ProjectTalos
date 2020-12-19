---
layout: default
title: Devlogs
---

# Devlogs

Browse all devlogs for Project Talos.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
	  {% unless post.title == "Welcome to Project Talos" %}
        <li><a href="https://osamahansari.github.io/ProjectTalos{{ post.url }}">{{ post.title }}</a></li>
	  {% endunless %}
    {% endfor %}
  </ul>
{% endfor %}
