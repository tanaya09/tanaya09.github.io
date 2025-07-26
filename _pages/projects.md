---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.5rem;
  padding: 1rem 0;
}
.project-card {
  background: #fff;
  border-radius: 12px;
  padding: 1rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  cursor: pointer;
  transition: transform 0.2s ease;
}
.project-card:hover {
  transform: translateY(-5px);
}
.project-image {
  width: 100%;
  border-radius: 10px;
}
.modal {
  display: none;
  position: fixed;
  z-index: 1000;
  padding-top: 60px;
  left: 0; top: 0;
  width: 100%; height: 100%;
  overflow: auto;
  background-color: rgba(0,0,0,0.6);
}
.modal-content {
  background-color: #fefefe;
  margin: auto;
  padding: 2rem;
  border-radius: 12px;
  width: 80%;
  max-width: 700px;
}
.close {
  color: #aaa;
  float: right;
  font-size: 24px;
  font-weight: bold;
  cursor: pointer;
}
</style>

<div class="projects-grid">
  {% for project in site.projects %}
    <div class="project-card" onclick="openModal('{{ forloop.index0 }}')">
      {% if project.header.image %}
        <img src="{{ project.header.image | relative_url }}" alt="{{ project.title }}" class="project-image"/>
      {% endif %}
      <h3 class="project-title">{{ project.title }}</h3>
      <p><strong>Tech Stack:</strong> {{ project.tech }}</p>
      <a href="{{ project.github }}" target="_blank">GitHub ↗</a>
    </div>
  {% endfor %}
</div>

<!-- Modals -->
{% for project in site.projects %}
  <div id="modal{{ forloop.index0 }}" class="modal">
    <div class="modal-content">
      <span class="close" onclick="closeModal('{{ forloop.index0 }}')">&times;</span>
      <h2>{{ project.title }}</h2>
      <p>{{ project.content | markdownify }}</p>
    </div>
  </div>
{% endfor %}

<script>
function openModal(id) {
  document.getElementById("modal" + id).style.display = "block";
}
function closeModal(id) {
  document.getElementById("modal" + id).style.display = "none";
}
window.onclick = function(event) {
  if (event.target.classList.contains('modal')) {
    event.target.style.display = "none";
  }
}
</script>
