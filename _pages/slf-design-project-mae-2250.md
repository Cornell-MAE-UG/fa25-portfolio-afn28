---
layout: default
title: SLF Design Project MAE 2250
permalink: /projects/slf-design-project-mae-2250/
---

# SLF Design Project MAE 2250

Explore the two SLF deliverables from MAE 2250 below.

<div class="gallery-container">
  <div class="project-gallery">
    {% for project in site.projects %}
      {% if project.title == "SLF Client Pitch" or project.title == "SLF Functional Prototype" %}
        <div class="gallery-item">
          <a href="{{ project.url | relative_url }}">
            <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
            <p>{{ project.title }}</p>
          </a>
        </div>
      {% endif %}
    {% endfor %}
  </div>
</div>
