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

      {% if project.header.image %}
        <img src="{{ project.header.image | relative_url }}" alt="{{ project.title }}" class="project-image"/>
      {% endif %}

      <h3 class="project-title">{{ project.title }}</h3>

      {% if project.tech %}
        <p class="project-tech"><strong>Tech Stack:</strong> {{ project.tech }}</p>
      {% endif %}

      {% if project.description %}
        <p class="project-desc">{{ project.description }}</p>
      {% elsif project.excerpt %}
        <p class="project-desc">{{ project.excerpt }}</p>
      {% endif %}

      {% if project.repo %}
        <a class="project-repo" href="{{ project.repo }}" target="_blank">View on GitHub</a>
      {% endif %}

    </div>
  {% endfor %}
</div>
