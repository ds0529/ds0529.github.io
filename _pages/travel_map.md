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

<div class="map-stats">
    <div class="stat-card">
        <div class="stat-number">8</div>
        <div class="stat-label">访问过的国家</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">1</div>
        <div class="stat-label">访问过的城市</div>
    </div>
    <div class="stat-card">
        <div class="stat-number">1</div>
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

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var map = L.map('map').setView([35, 105], 4);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);

    // L.marker([39.9042, 116.4074]).addTo(map).bindPopup("北京");
    // L.marker([31.2304, 121.4737]).addTo(map).bindPopup("上海");

    const places = [
      {name: "漠河",      lat: 52.9736, lon: 122.5370},
      {name: "哈尔滨",    lat: 45.8038, lon: 126.5349},
      {name: "延吉",      lat: 42.8915, lon: 129.5150},
      {name: "大连",      lat: 38.9140, lon: 121.6147},
      {name: "承德",      lat: 40.9518, lon: 117.9392},
      {name: "秦皇岛",    lat: 39.9411, lon: 119.5996},
      {name: "北京",      lat: 39.9042, lon: 116.4074},
      {name: "天津",      lat: 39.3434, lon: 117.3616},
      {name: "赤峰",      lat: 42.2579, lon: 118.9568},
      {name: "锡林格勒",  lat: 43.9333, lon: 116.0833}, // Xilinhot / Xilingol area
      {name: "大同",      lat: 40.1138, lon: 113.3001},
      {name: "济南",      lat: 36.6683, lon: 117.0209},
      {name: "青岛",      lat: 36.0671, lon: 120.3826},
      {name: "洛阳",      lat: 34.6197, lon: 112.4540},
      {name: "南京",      lat: 32.0603, lon: 118.7969},
      {name: "苏州",      lat: 31.2989, lon: 120.5853},
      {name: "无锡",      lat: 31.4912, lon: 120.3120},
      {name: "常州",      lat: 31.7723, lon: 119.9747},
      {name: "扬州",      lat: 32.3935, lon: 119.4129},
      {name: "淮安",      lat: 33.4996, lon: 119.0153},
      {name: "上海",      lat: 31.2304, lon: 121.4737},
      {name: "杭州",      lat: 30.2741, lon: 120.1551},
      {name: "舟山",      lat: 29.9850, lon: 122.2072},
      {name: "合肥",      lat: 31.8206, lon: 117.2272},
      {name: "黄山",      lat: 29.7139, lon: 118.2936},
      {name: "厦门",      lat: 24.4798, lon: 118.0895},
      {name: "泉州",      lat: 24.8739, lon: 118.6756},
      {name: "广州",      lat: 23.1291, lon: 113.2644},
      {name: "深圳",      lat: 22.5431, lon: 114.0579},
      {name: "佛山",      lat: 23.0215, lon: 113.1214},
      {name: "柳州",      lat: 24.3141, lon: 109.4280},
      {name: "桂林",      lat: 25.2736, lon: 110.2905},
      {name: "北海",      lat: 21.4850, lon: 109.1200},
      {name: "海口",      lat: 20.0440, lon: 110.1999},
      {name: "三亚",      lat: 18.2528, lon: 109.5119},
      {name: "武汉",      lat: 30.5928, lon: 114.3055},
      {name: "宜昌",      lat: 30.6970, lon: 111.2908},
      {name: "荆门",      lat: 31.0355, lon: 112.2044},
      {name: "神农架",    lat: 31.4889, lon: 110.6749},
      {name: "长沙",      lat: 28.2282, lon: 112.9388},
      {name: "张家界",    lat: 29.1171, lon: 110.4792},
      {name: "吉首",      lat: 28.3056, lon: 109.7097},
      {name: "南昌",      lat: 28.6820, lon: 115.8579},
      {name: "九江",      lat: 29.7053, lon: 116.0019},
      {name: "萍乡",      lat: 27.6229, lon: 113.8598},
      {name: "成都",      lat: 30.5728, lon: 104.0668},
      {name: "重庆",      lat: 29.5630, lon: 106.5516},
      {name: "贵阳",      lat: 26.6470, lon: 106.6302},
      {name: "凯里",      lat: 26.7081, lon: 107.9862},
      {name: "昆明",      lat: 25.0389, lon: 102.7186},
      {name: "大理",      lat: 25.6065, lon: 100.2250},
      {name: "丽江",      lat: 26.8721, lon: 100.2330},
      {name: "西安",      lat: 34.3416, lon: 108.9398},
      {name: "银川",      lat: 38.4872, lon: 106.2309},
      {name: "敦煌",      lat: 40.1421, lon: 94.6620},
      {name: "嘉峪关",    lat: 39.8028, lon: 98.2770},
      {name: "张掖",      lat: 38.9329, lon: 100.4500},
      {name: "西宁",      lat: 36.6171, lon: 101.7782},
      {name: "海西",      lat: 37.3730, lon: 97.3700},   // 海西州（德令哈 / Delingha）附近代表点
      {name: "喀什",      lat: 39.4704, lon: 75.9898}
    ];
  
    // 如果你还没定义 map，请先定义，例如：
    // var map = L.map('map').setView([35, 105], 4);
    // 并加载 tileLayer
  
    places.forEach(function(p) {
      L.marker([p.lat, p.lon])
       .addTo(map)
       .bindPopup(p.name);
    });
  });
</script>
{% endraw %}
