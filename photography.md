---
layout: default
title: Kandice Lu - Photography
permalink: /photography/
---

# Photography

A selection of my work.

<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 16px;
  margin-top: 1.5rem;
}

.gallery img {
  width: 100%;
  height: 300px;
  object-fit: cover;
  border-radius: 6px;
  cursor: pointer;
}

/* Lightbox */
.lightbox {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.9);
  display: none;
  align-items: center;
  justify-content: center;
  z-index: 9999;
}

.lightbox img {
  max-width: 95vw;
  max-height: 95vh;
  object-fit: contain;
}

.lightbox:target {
  display: flex;
}

.lightbox a.close {
  position: absolute;
  inset: 0;
}
</style>

<div class="gallery">
{% assign photos = site.static_files | where_exp: "file", "file.path contains '/assets/images/photography/'" %}
{% for photo in photos %}
  <a href="#{{ forloop.index }}">
    <img src="{{ site.baseurl }}{{ photo.path }}" alt="">
  </a>
{% endfor %}
</div>

{% for photo in photos %}
<div id="{{ forloop.index }}" class="lightbox">
  <a href="#" class="close"></a>
  <img src="{{ site.baseurl }}{{ photo.path }}">
</div>
{% endfor %}

<script>
document.addEventListener("keydown", function (e) {
  const total = {{ photos | size }};
  const hash = window.location.hash;

  if (!hash) return;

  const current = parseInt(hash.replace("#", ""));

  if (e.key === "Escape") {
    history.replaceState(null, null, " ");
  }

  if (e.key === "ArrowRight" && current < total) {
    window.location.hash = current + 1;
  }

  if (e.key === "ArrowLeft" && current > 1) {
    window.location.hash = current - 1;
  }
});
</script>
