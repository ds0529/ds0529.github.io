---
layout: archive
permalink: /travel_map/
title: "Travel Map"
author_profile: true
redirect_from:
  - /wordpress/travel_map/
---

{% raw %}
<div id="map" style="height:600px; width:100%;"></div>

<div class="map-stats">
    <div class="stat-card">
        <div class="stat-number">9</div>
        <div class="stat-label">访问过的国家</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">74</div>
        <div class="stat-label">访问过的城市</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">32</div>
        <div class="stat-label">访问过的省份</div>
    </div>
</div>

<style>
    .map-stats {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 1.5rem;
        margin: 2rem 0;
    }
    
    .stat-card {
        background: #f8f9fa;
        padding: 1.5rem;
        border-radius: 8px;
        text-align: center;
        border-left: 4px solid #159957;
        box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
    }
    
    .stat-number {
        font-size: 2.2rem;
        font-weight: bold;
        color: #159957;
        margin-bottom: 0.5rem;
        line-height: 1;
    }
    
    .stat-label {
        font-size: 0.95rem;
        color: #6c757d;
        text-transform: uppercase;
        letter-spacing: 0.5px;
    }
</style>

<!-- Leaflet CSS -->
<link rel="stylesheet" href="https://unpkg.com/leaflet/dist/leaflet.css" />

<!-- Leaflet JS -->
<script src="https://unpkg.com/leaflet/dist/leaflet.js"></script>

<!-- Countries .geo.json: https://github.com/johan/world.geo.json/tree/master/countries -->
<script>
  document.addEventListener("DOMContentLoaded", function() {
    var map = L.map('map').setView([35, 105], 4);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);

    function addCountry(url, fillColor) {
      fetch(url)
        .then(r => r.json())
        .then(data => {
          L.geoJSON(data, {
            style: {
              color: "#000000",
              weight: 1,
              fillColor: fillColor,
              fillOpacity: 0.4
            }
          }).addTo(map);
        });
    }
    
    addCountry("/files/map_data/CHN.geo.json", "#ffcccc");
    addCountry("/files/map_data/JPN.geo.json", "#cce5ff");
    addCountry("/files/map_data/THA.geo.json", "#ccffcc");
    addCountry("/files/map_data/TUR.geo.json", "#ffe5cc");
    addCountry("/files/map_data/GEO.geo.json", "#e5ccff");
    addCountry("/files/map_data/KOR.geo.json", "#ffffcc");
    addCountry("/files/map_data/RUS.geo.json", "#e5e5e5");
    addCountry("/files/map_data/VNM.geo.json", "#ccffff");

    fetch("/files/map_data/cities.json")
      .then(r => r.json())
      .then(cities => {
        cities.forEach(city => {
          let popupContent = `<div style="text-align:center;">
            <h4>${city.name}</h4>`;
          if (city.date) popupContent += `<p>${city.date}</p>`;
          if (city.image) popupContent += `<img src="assets/images/${city.image}" style="width:150px;height:auto;margin-top:5px;" />`;
          popupContent += `</div>`;
          L.marker([city.lat, city.lon]).addTo(map).bindPopup(popupContent);
        });
      });
  });
</script>
{% endraw %}
