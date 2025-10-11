---
layout: default
title: Kandice Lu - Projects
permalink: /projects/
---

<div class="mb-4">
  <a href="{{ '/' | relative_url }}" class="btn btn-secondary">
    &larr; Back to Home
  </a>
</div>

<h1 class="mb-4 page-title">{{ page.title }}</h1>


<div class="row g-4">
  {% for project in site.projects %}
    <div class="col-sm-6 col-md-4 col-lg-4">
      <a href="{{ project.url | relative_url }}" class="card-link-wrapper text-decoration-none">
        <div class="card h-100 project-card">

          <!-- Project First Image -->
          {% if project.images and project.images.size > 0 %}
            <img src="{{ project.images[0] | relative_url }}" 
                 class="card-img-top project-thumb" 
                 alt="{{ project.imagealt[0] | default: project.title }}">
          {% elsif project.image %}
            <img src="{{ project.image | relative_url }}" 
                 class="card-img-top project-thumb" 
                 alt="{{ project.imagealt | default: project.title }}">
          {% endif %}

          <!-- Project Info -->
          <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            {% if project.description %}
              <p class="card-text text-muted">{{ project.description }}</p>
            {% endif %}
          </div>

        </div>
      </a>
    </div>
  {% endfor %}
</div>

<style>
  .project-thumb {
    height: 200px;       /* Fixed height for thumbnails */
    object-fit: cover;   /* Crop to fill card top */
    width: 100%;
  }
  h1.page-title {
  font-size: 1.75rem;   /* adjust smaller than default */
  font-weight: 600;  /* optional */
  margin-bottom: 0rem;
}

  .card-link-wrapper {
    display: block;
    color: inherit;
  }
  
  .project-card {
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .card-link-wrapper:hover .project-card {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  }
</style>
