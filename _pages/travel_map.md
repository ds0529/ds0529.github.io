---
layout: archive
permalink: /travel_map/
title: "travel map"
author_profile: true
redirect_from:
  - /wordpress/travel_map/
---

{% raw %}
<div id="map" style="height:600px; width:100%;"></div>

<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var map = L.map('map').setView([35, 105], 4);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);

    L.marker([39.9042, 116.4074]).addTo(map).bindPopup("Beijing");
    L.marker([31.2304, 121.4737]).addTo(map).bindPopup("Shanghai");
  });
</script>
{% endraw %}

{% include map.html %}
