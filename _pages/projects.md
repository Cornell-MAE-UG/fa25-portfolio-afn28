---
layout: default
title: Andrew Nocilly - Portfolio
permalink: /projects/
---

<div class="toc-box">
  <strong>Table of Contents</strong>
  <ul style="list-style: none; padding-left: 0;">
    {% for project in site.projects %}
      <li>
        <a href="#{{ project.slug }}" class="toc-link" data-project="{{ project.slug }}">
          {{ project.title }}
        </a>
      </li>
    {% endfor %}
  </ul>
</div>

<div class="gallery-container">
  <div class="project-gallery">
    {% for project in site.projects %}
      <div class="gallery-item" id="{{ project.slug }}" data-project="{{ project.slug }}">
        <a href="{{ project.url | relative_url }}">
          <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
          <p>{{ project.title }}</p>
        </a>
      </div>
    {% endfor %}
  </div>
</div>

<script>
    document.querySelectorAll(".toc-link").forEach(link => {
        link.addEventListener("click", function (e) {
            e.preventDefault();

            const slug = this.dataset.project;

            document.querySelectorAll(".gallery-item").forEach(item => {
                item.classList.remove("highlight");
            });

            const target = document.querySelector(`.gallery-item[data-project="${slug}"]`);
            if (target) {
                target.classList.add("highlight");
                
                setTimeout(() => {
                    target.classList.remove("highlight");
                }, 2000);
            }
        });
    });
</script>