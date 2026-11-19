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

Save each project's `index.html` under `_projects/<project-name>/`. Set a permalink in its front matter, then it will appear below automatically:

```yaml
---
layout: school-project
title: Project name
permalink: /school/project-name/
---
```

{% if site.projects.size > 0 %}
<ul>
  {% for project in site.projects %}
  <li><a href="{{ project.url | relative_url }}">{{ project.title | default: project.name }}</a></li>
  {% endfor %}
</ul>
{% else %}
<p>Projects will appear here when added.</p>
{% endif %}
