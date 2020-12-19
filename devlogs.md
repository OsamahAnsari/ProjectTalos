---
layout: default
title: Devlogs
---

# Devlogs

Check out the full guide for how to make a game incorporating ML Agents.

<a href="https://osamahansari.github.io/ProjectTalos/2020/12/16/full-guide/">ML Agents in Games - Full Guide</a>

Browse all other devlogs for Project Talos.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
	  {% unless post.title == "Welcome to Project Talos" or post.title == "ML Agents in Games - Full Guide" %}
        <li><a href="https://osamahansari.github.io/ProjectTalos{{ post.url }}">{{ post.title }}</a></li>
	  {% endunless %}
    {% endfor %}
  </ul>
{% endfor %}
