---
layout: archive
title: "Education"
permalink: /education/
author_profile: true
---

{% include base_path %}

{% for edu in site.data.education %}
  <section class="education-item">
    <h4>{{ edu.degree }}</h4>
    <p>{{ edu.institution }} – ({{ edu.start_date | date: "%Y-%m" }} – 
      {% if edu.end_date == "present" %}Present{% else %}{{ edu.end_date | date: "%Y-%m" }}{% endif %})
    </p>
  </section>

  {% unless forloop.last %}
    <hr />
  {% endunless %}
{% endfor %}

