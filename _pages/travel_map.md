---
layout: archive
permalink: /travel_map/
title: "travel map"
author_profile: false
redirect_from:
  - /wordpress/travel_map/
---

{% raw %}
<div id="map" style="height:600px; width:100%;"></div>

<div class="map-stats">
    <div class="stat-card">
        <div class="stat-number">12</div>
        <div class="stat-label">访问过的国家</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">24</div>
        <div class="stat-label">访问过的城市</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">5</div>
        <div class="stat-label">今年新目的地</div>
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

<script>
  document.addEventListener("DOMContentLoaded", function() {
    // 初始化地图
    var map = L.map('map').setView([35, 105], 4);

    // 加载 OpenStreetMap 图层
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);

    // 遍历 Jekyll 数据文件
    {% for loc in site.data.travel_map %}
      L.marker([{{ loc.lat }}, {{ loc.lon }}])
        .addTo(map)
        .bindPopup("<b>{{ loc.name }}</b>");
    {% endfor %}
  });
</script>

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
