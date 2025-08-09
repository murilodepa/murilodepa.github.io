---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}


<h1>{{ site.data.personal.name }}</h1>
<p>
  <strong>Nationality:</strong> {{ site.data.personal.nationality }} • 
  <strong>Marital Status:</strong> {{ site.data.personal.marital_status }} • 
  <strong>Date of Birth:</strong> {{ site.data.personal.dob }}
</p>
<p>
  <strong>Address:</strong> {{ site.data.personal.address }}
</p>
<p>
  <strong>Email:</strong> 
  {% for email in site.data.personal.emails %}
    {{ email }}{% unless forloop.last %} • {% endunless %}
  {% endfor %}
</p>

<h2>Professional Objective</h2>
<p>{{ site.data.objective.objective }}</p>

<h2>Summary of Qualifications</h2>
<div>
  {{ site.data.summary.summary | markdownify }}
</div>

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
      <ul>
        <li>
          {{ experience.positions[0].title }}
          {% if experience.positions[0].start_date == nil and experience.positions[0].end_date == nil %}
            <!-- Não mostrar datas para posição sem datas -->
          {% else %}
            – ({{ experience.start_date | date: "%b %Y" }} – 
            {% if experience.end_date == "present" %}Present{% else %}{{ experience.end_date | date: "%b %Y" }}{% endif %})
          {% endif %}
        </li>
      </ul>
    {% endif %}
  </section>

  <hr />
{% endfor %}





Education
======
* Ph.D in Version Control Theory, GitHub University, 2018 (expected)
* M.S. in Jekyll, GitHub University, 2014
* B.S. in GitHub, GitHub University, 2012

Work experience
======
* Spring 2024: Academic Pages Collaborator
  * GitHub University
  * Duties includes: Updates and improvements to template
  * Supervisor: The Users

* Fall 2015: Research Assistant
  * GitHub University
  * Duties included: Merging pull requests
  * Supervisor: Professor Hub

* Summer 2015: Research Assistant
  * GitHub University
  * Duties included: Tagging issues
  * Supervisor: Professor Git
  
Skills
======
* Skill 1
* Skill 2
  * Sub-skill 2.1
  * Sub-skill 2.2
  * Sub-skill 2.3
* Skill 3

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently signed in to 43 different slack teams
