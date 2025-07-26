---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
  padding: 1rem 0;
  align-items: start;
}

.project-card {
  background: #fff;
  border-radius: 10px;
  padding: 1rem;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  transition: transform 0.2s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  text-align: left;
  cursor: pointer;
}

.project-card:hover {
  transform: scale(1.02);
}

.project-image {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: 0.5rem;
}

.project-title {
  font-size: 1.1rem;
  margin: 0.5rem 0;
}

.project-card a {
  margin-top: auto;
  color: #007acc;
  font-weight: 500;
  text-decoration: none;
}

.modal {
  display: none;
  position: fixed;
  z-index: 1000;
  left: 0; top: 0;
  width: 100%; height: 100%;
  overflow: auto;
  background-color: rgba(0,0,0,0.7);
}

.modal-content {
  background: #fff;
  margin: 5% auto;
  padding: 2rem;
  border-radius: 10px;
  width: 90%;
  max-width: 600px;
  position: relative;
}

.close {
  position: absolute;
  top: 10px;
  right: 16px;
  font-size: 24px;
  font-weight: bold;
  color: #aaa;
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
      <a href="{{ project.github }}" target="_blank" onclick="event.stopPropagation();">GitHub ↗</a>
    </div>
  {% endfor %}
</div>

<!-- Modals -->
{% for project in site.projects %}
  <div id="modal{{ forloop.index0 }}" class="modal">
    <div class="modal-content">
      <span class="close" onclick="closeModal('{{ forloop.index0 }}')">&times;</span>
      <h2>{{ project.title }}</h2>
      <p><strong>Tech Stack:</strong> {{ project.tech }}</p>
      <div>{{ project.content | markdownify }}</div>
      <p><a href="{{ project.github }}" target="_blank">View on GitHub ↗</a></p>
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
