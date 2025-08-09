---
layout: archive
title: "Experience"
permalink: /experience/
author_profile: true
---

{% include base_path %}

{% for experience in site.data.experience %}
  <section class="experience-company">
    <h3>
      {{ experience.company }} – 
      ({{ experience.start_date | date: "%b %Y" }} – 
      {% if experience.end_date == "present" %}Present{% else %}{{ experience.end_date | date: "%b %Y" }}{% endif %})
    </h3>

    <p>{{ experience.description }}</p>

    {% if experience.positions.size > 1 %}
      <ul>
      {% for pos in experience.positions %}
        <li>
          {{ pos.title }}
          {% if pos.start_date and pos.end_date %}
            – ({{ pos.start_date | date: "%b %Y" }} – 
            {% if pos.end_date == "present" %}Present{% else %}{{ pos.end_date | date: "%b %Y" }}{% endif %})
          {% endif %}
        </li>
      {% endfor %}
      </ul>
    {% else %}
      <!-- Só uma posição -->
      <p>
        {{ experience.positions[0].title }}
        {% if experience.positions[0].start_date == nil and experience.positions[0].end_date == nil %}
          <!-- Não mostrar datas para posição sem datas -->
        {% else %}
          – ({{ experience.start_date | date: "%b %Y" }} – 
          {% if experience.end_date == "present" %}Present{% else %}{{ experience.end_date | date: "%b %Y" }}{% endif %})
        {% endif %}
      </p>
    {% endif %}
  </section>
{% endfor %}

