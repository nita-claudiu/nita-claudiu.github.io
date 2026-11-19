---
layout: page
title: Home / School
description: School work and projects.
permalink: /school/
---

{% if site.projects.size > 0 %}
<ul>
  {% for project in site.projects %}
  <li><a href="{{ project.url | relative_url }}">{{ project.title | default: project.name }}</a></li>
  {% endfor %}
</ul>
{% else %}
<p>No projects yet.</p>
{% endif %}
