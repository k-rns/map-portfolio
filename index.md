---
layout: default
title: 30 Day Map Challenge
---
<section class="page-intro">
  <h1>30 DAY MAP CHALLENGE</h1>
  <p>
    30 maps exploring data through cartography.
  </p>
</section>
<div class="map-grid">
  <a href="{{ site.maps[0].url | relative_url }}" class="map-card">
    <img src="{{ site.maps[0].image | relative_url }}" alt="{{ site.maps[0].title }}" class="map-card-image">
    <div class="map-card-day">Day 01</div>
    <div class="map-card-title">{{ site.maps[0].title }}</div>
  </a>
</div>
