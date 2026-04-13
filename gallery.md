---
layout: page
title: Photo Gallery
subtitle: Outreach in Action!
comments: false
---


Enjoy some photo galleries from our various events!  


<!-- --- NO TOUCH BELOW HERE.  Add more photos in _data/gallery_page.yml --- -->


<!-- --- Gallery grid --- -->
<div class="gallery">
  {% for img in site.data.gallery_page %}  <!-- edit gallery_page to different .yml file, if a different gallery is desired --- -->
  <div class="gallery-item">
    <a href="#img{{ forloop.index }}">
      <img src="{{ img.file }}" alt="{{ img.alt }}">
      <div class="gallery-caption">{{ img.caption }}</div>
    </a>
  </div>
  {% endfor %}
</div>
<!-- --- Lightboxes --- -->
{% for img in site.data.gallery_page %}  <!-- edit gallery_page to different .yml file, if a different gallery is desired --- -->
<div id="img{{ forloop.index }}" class="lightbox">
  <div class="lightbox-image-wrapper">
    <a href="#!" class="close">×</a>
    <img src="{{ img.file }}" alt="{{ img.alt }}">
    <div class="lightbox-caption">{{ img.caption }}</div>
    <!-- Prev/Next arrows -->
    <a href="#img{% if forloop.first %}{{ site.data.gallery | size }}{% else %}{{ forloop.index0 }}{% endif %}" class="prev">&#10094;</a>
    <a href="#img{% if forloop.last %}1{% else %}{{ forloop.index | plus:1 }}{% endif %}" class="next">&#10095;</a>
  </div>
</div>
{% endfor %}
