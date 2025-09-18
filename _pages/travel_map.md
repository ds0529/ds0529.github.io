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

<script>
  document.addEventListener("DOMContentLoaded", function() {
    var map = L.map('map').setView([35, 105], 4);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap contributors'
    }).addTo(map);

    // 国内
    // 黑龙江
    L.marker([52.9736, 122.5370]).addTo(map).bindPopup("漠河");
    L.marker([45.8038, 126.5349]).addTo(map).bindPopup("哈尔滨");
    // 吉林
    L.marker([42.8915, 129.5150]).addTo(map).bindPopup("延吉");
    // 辽宁
    L.marker([38.9140, 121.6147]).addTo(map).bindPopup("大连");
    // 河北
    L.marker([40.9518, 117.9392]).addTo(map).bindPopup("承德");
    L.marker([39.9411, 119.5996]).addTo(map).bindPopup("秦皇岛");
    // 北京
    L.marker([39.9042, 116.4074]).addTo(map).bindPopup("北京");
    // 天津
    L.marker([39.3434, 117.3616]).addTo(map).bindPopup("天津");
    // 内蒙古
    L.marker([42.2579, 118.9568]).addTo(map).bindPopup("赤峰");
    L.marker([43.9333, 116.0833]).addTo(map).bindPopup("锡林格勒");
    // 山西
    L.marker([40.1138, 113.3001]).addTo(map).bindPopup("大同");
    // 山东
    L.marker([36.6683, 117.0209]).addTo(map).bindPopup("济南");
    L.marker([36.0671, 120.3826]).addTo(map).bindPopup("青岛");
    // 河南
    L.marker([34.6197, 112.4540]).addTo(map).bindPopup("洛阳");
    // 江苏
    L.marker([32.0603, 118.7969]).addTo(map).bindPopup("南京");
    L.marker([31.2989, 120.5853]).addTo(map).bindPopup("苏州");
    L.marker([31.4912, 120.3120]).addTo(map).bindPopup("无锡");
    L.marker([31.7723, 119.9747]).addTo(map).bindPopup("常州");
    L.marker([32.3935, 119.4129]).addTo(map).bindPopup("扬州");
    L.marker([33.4996, 119.0153]).addTo(map).bindPopup("淮安");
    // 上海
    L.marker([31.2304, 121.4737]).addTo(map).bindPopup("上海");
    // 浙江
    L.marker([30.2741, 120.1551]).addTo(map).bindPopup("杭州");
    L.marker([29.9850, 122.2072]).addTo(map).bindPopup("舟山");
    // 安徽
    L.marker([31.8206, 117.2272]).addTo(map).bindPopup("合肥");
    L.marker([29.7139, 118.2936]).addTo(map).bindPopup("黄山");
    // 福建
    L.marker([24.4798, 118.0895]).addTo(map).bindPopup("厦门");
    L.marker([24.8739, 118.6756]).addTo(map).bindPopup("泉州");
    // 广东
    L.marker([23.1291, 113.2644]).addTo(map).bindPopup("广州");
    L.marker([22.5431, 114.0579]).addTo(map).bindPopup("深圳");
    L.marker([23.0215, 113.1214]).addTo(map).bindPopup("佛山");
    // 香港
    L.marker([22.3193, 114.1694]).addTo(map).bindPopup("香港");
    // 澳门
    L.marker([22.1987, 113.5439]).addTo(map).bindPopup("澳门");
    // 广西
    L.marker([24.3141, 109.4280]).addTo(map).bindPopup("柳州");
    L.marker([25.2736, 110.2905]).addTo(map).bindPopup("桂林");
    L.marker([21.4850, 109.1200]).addTo(map).bindPopup("北海");
    // 海南
    L.marker([20.0440, 110.1999]).addTo(map).bindPopup("海口");
    L.marker([18.2528, 109.5119]).addTo(map).bindPopup("三亚");
    // 湖北
    L.marker([30.5928, 114.3055]).addTo(map).bindPopup("武汉");
    L.marker([30.6970, 111.2908]).addTo(map).bindPopup("宜昌");
    L.marker([31.0355, 112.2044]).addTo(map).bindPopup("荆门");
    L.marker([31.4889, 110.6749]).addTo(map).bindPopup("神农架");
    // 湖南
    L.marker([28.2282, 112.9388]).addTo(map).bindPopup("长沙");
    L.marker([29.1171, 110.4792]).addTo(map).bindPopup("张家界");
    L.marker([28.3056, 109.7097]).addTo(map).bindPopup("吉首");
    // 江西
    L.marker([28.6820, 115.8579]).addTo(map).bindPopup("南昌");
    L.marker([29.7053, 116.0019]).addTo(map).bindPopup("九江");
    L.marker([27.6229, 113.8598]).addTo(map).bindPopup("萍乡");
    // 四川
    L.marker([30.5728, 104.0668]).addTo(map).bindPopup("成都");
    // 重庆
    L.marker([29.5630, 106.5516]).addTo(map).bindPopup("重庆");
    // 贵州
    L.marker([26.6470, 106.6302]).addTo(map).bindPopup("贵阳");
    L.marker([26.7081, 107.9862]).addTo(map).bindPopup("凯里");
    // 云南
    L.marker([25.0389, 102.7186]).addTo(map).bindPopup("昆明");
    L.marker([25.6065, 100.2250]).addTo(map).bindPopup("大理");
    L.marker([26.8721, 100.2330]).addTo(map).bindPopup("丽江");
    // 陕西
    L.marker([34.3416, 108.9398]).addTo(map).bindPopup("西安");
    // 宁夏
    L.marker([38.4872, 106.2309]).addTo(map).bindPopup("银川");
    // 甘肃
    L.marker([40.1421, 94.6620]).addTo(map).bindPopup("敦煌");
    L.marker([39.8028, 98.2770]).addTo(map).bindPopup("嘉峪关");
    L.marker([38.9329, 100.4500]).addTo(map).bindPopup("张掖");
    // 青海
    L.marker([36.6171, 101.7782]).addTo(map).bindPopup("西宁");
    L.marker([37.3730, 97.3700]).addTo(map).bindPopup("海西");
    // 新疆
    L.marker([39.4704, 75.9898]).addTo(map).bindPopup("喀什");

    // // 国外
    // // 日本
    // L.marker([35.6895, 139.6917]).addTo(map).bindPopup("东京");
    // L.marker([35.4437, 139.6380]).addTo(map).bindPopup("横滨");
    // L.marker([34.6937, 135.5023]).addTo(map).bindPopup("大阪");
    // L.marker([35.0116, 135.7681]).addTo(map).bindPopup("京都");
    // // 泰国
    // L.marker([13.7563, 100.5018]).addTo(map).bindPopup("曼谷");
    // // 土耳其
    // L.marker([41.0082, 28.9784]).addTo(map).bindPopup("伊斯坦布尔");
    // // 格鲁吉亚
    // L.marker([41.7151, 44.8271]).addTo(map).bindPopup("第比利斯");
    // L.marker([42.5128, 42.5128]).addTo(map).bindPopup("卡兹别克"); // 高加索地区 Mt. Kazbek，近似坐标
    // // 韩国
    // L.marker([37.5665, 126.9780]).addTo(map).bindPopup("首尔");
    // // 俄罗斯
    // L.marker([43.1155, 131.8855]).addTo(map).bindPopup("海参崴"); // 符拉迪沃斯托克
    // // 新加坡
    // L.marker([1.3521, 103.8198]).addTo(map).bindPopup("新加坡");
    // // 越南
    // L.marker([21.0278, 105.8342]).addTo(map).bindPopup("河内");

  });
</script>
{% endraw %}
