---
layout: page
title: Achievements
description: Achievements by year.
permalink: /achievements/
---

<section class="achievements">
  <h2>2026</h2>
  {% assign entries = site.data.achievements["2026"] %}
  {% if entries and entries.size > 0 %}
  <ul class="achievement-list">
    {% for achievement in entries %}
    <li class="achievement-card{% if achievement.class %} {{ achievement.class | escape }}{% endif %}">
      <div class="achievement-heading">
        {% if achievement.title %}<h3>{{ achievement.title | escape }}</h3>{% endif %}
        {% if achievement.place == 1 %}<span class="achievement-medal gold" aria-label="1st place">1st</span>
        {% elsif achievement.place == 2 %}<span class="achievement-medal silver" aria-label="2nd place">2nd</span>
        {% elsif achievement.place == 3 %}<span class="achievement-medal bronze" aria-label="3rd place">3rd</span>{% endif %}
      </div>
      {% if achievement.custom_html %}
        {{ achievement.custom_html }}
      {% else %}
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
