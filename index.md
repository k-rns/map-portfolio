---
layout: default
title: 30 Day Map Challenge
---
<section class="page-intro">
  <h1>30 DAY MAP CHALLENGE</h1>
  <p>Each day of this challenge turns open data (geographic, environmental, statistical) into a map that makes patterns easier to see and act on. </p>
  <p>A map turns raw data into real information: something you can read, compare, and act on, especially once it combines several sources at once. </p>
  <p>That's what I'm after here: using GIS to find connections a single dataset can't show by itself.</p>
</section>

<div class="map-grid">
{% comment %} Loop through day numbers 1 to 30, one card per day {% endcomment %}
{% for i in (1..30) %}

  {% comment %} Turn the number into a 2-digit string: 1 -> "01", 23 -> "23" {% endcomment %}
  {% assign day_str = i | prepend: "00" | slice: -2, 2 %}

  {% comment %} Look through _maps/ for a file whose front-matter "day:" matches this loop number {% endcomment %}
  {% comment %} If no file has this day yet, "match" will be empty {% endcomment %}
  {% assign match = site.maps | where: "day", i | first %}

  {% if match and match.published != false %}
    {% comment %} A map file exists for this day -> show a real, clickable thumbnail {% endcomment %}
    <a href="{{ match.url | relative_url }}" class="map-card">
      <img src="{{ match.image | relative_url }}" alt="{{ match.title }}" class="map-card-image">
      <div class="map-card-day">Day {{ day_str }}</div>
      <div class="map-card-title">{{ match.title }}</div>
    </a>
  {% else %}
    {% comment %} No map file yet for this day -> show an empty grey placeholder box {% endcomment %}
    <div class="map-card map-card-placeholder">
      <div class="map-card-image"></div>
      <div class="map-card-day">Day {{ day_str }}</div>
    </div>
  {% endif %}

{% endfor %}
</div>
