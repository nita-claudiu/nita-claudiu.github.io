---
layout: page
title: Home / School
description: School work and projects.
permalink: /school/
---

This page collects my school work and projects. Each project can be a standalone site in its own folder under `school/`.

```yaml
---
layout: school-project
title: Project name
permalink: /school/project-name/
---
```

Put this at the top of `school/project-name/index.html`, then add the project's HTML below it. The standalone layout has a single back button and does not include the blog header, sidebar, or other site navigation.

Add an entry to `_data/school_projects.yml` so it appears below:

```yaml
- title: Project name
  url: /school/project-name/
```

{% if site.data.school_projects and site.data.school_projects.size > 0 %}
<ul>
  {% for project in site.data.school_projects %}
  <li><a href="{{ project.url | relative_url }}">{{ project.title }}</a></li>
  {% endfor %}
</ul>
{% else %}
<p>Projects will appear here when added.</p>
{% endif %}
