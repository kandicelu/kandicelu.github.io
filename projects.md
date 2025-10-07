---
layout: default
title: Kandice Lu - Projects
permalink: /projects/
---

<h1>{{ page.title }}</h1>

<ul class="list-group">
{% for project in site.projects %}
  <li class="list-group-item">
    <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    {% if project.description %}
      <p class="mb-0 text-muted">{{ project.description }}</p>
    {% endif %}
  </li>
{% endfor %}
</ul>
