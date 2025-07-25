---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

<div class="projects-grid">
  {% for project in site.projects %}
    <div class="project-card">
      <a href="{{ project.url | relative_url }}">
        {% if project.header.image %}
          <img src="{{ project.header.image | relative_url }}" alt="{{ project.title }}" class="project-image"/>
        {% endif %}
        <h3 class="project-title">{{ project.title }}</h3>
        <p class="project-excerpt">{{ project.excerpt }}</p>
      </a>
    </div>
  {% endfor %}
</div>

