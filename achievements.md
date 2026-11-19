---
layout: page
title: Achievements
description: Achievements by year.
permalink: /achievements/
---

<section class="achievements">
  <h2>2026</h2>
  {% assign entries = site.data.achievements %}
  {% if entries and entries.size > 0 %}
  <ul class="achievement-list">
    {% for achievement in entries %}
    <li{% if achievement.class %} class="{{ achievement.class | escape }}"{% endif %}>
      {% if achievement.custom_html %}
        {{ achievement.custom_html }}
      {% else %}
        {% if achievement.place == 1 %}<span class="achievement-medal" role="img" aria-label="1st place">🥇</span>
        {% elsif achievement.place == 2 %}<span class="achievement-medal" role="img" aria-label="2nd place">🥈</span>
        {% elsif achievement.place == 3 %}<span class="achievement-medal" role="img" aria-label="3rd place">🥉</span>{% endif %}
        {% if achievement.title %}<span>{{ achievement.title | escape }}</span>{% endif %}
        {% if achievement.description %}<p>{{ achievement.description | escape }}</p>{% endif %}
        {% if achievement.date %}<time>{{ achievement.date | escape }}</time>{% endif %}
      {% endif %}
    </li>
    {% endfor %}
  </ul>
  {% else %}
  <p>No achievements listed yet.</p>
  {% endif %}
</section>
