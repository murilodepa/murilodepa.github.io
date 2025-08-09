---
layout: archive
title: "Education"
permalink: /education/
author_profile: true
---

{% include base_path %}

<ul>
  {% for edu in site.data.education %}
  <li>
    • {{ edu.degree }}.<br />
    {{ edu.institution }} – ({{ edu.start_date | date: "%b %Y" }} – 
    {% if edu.end_date == "present" %}Present{% else %}{{ edu.end_date | date: "%b %Y" }}{% endif %}).
  </li>
  <hr />
  {% endfor %}
</ul>

