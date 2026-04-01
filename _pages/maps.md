---
layout: page
title: Maps / Mapas
permalink: /maps/
description: Interactive maps showing key research territories in Bogotá.
nav: true
nav_order: 3
---

This map shows the key territories where hidden poverty concentrates in Bogotá. Click each marker to learn more. Interactive data layers from Sisbén IV and ILSIS will be added as the research progresses.

*Este mapa muestra los territorios clave donde se concentra la pobreza oculta en Bogotá. Haz clic en cada marcador para más información.*

<div id="map" style="height: 500px; width: 100%; border-radius: 8px; margin: 20px 0;"></div>

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

<script>
var map = L.map('map').setView([4.6097, -74.0817], 12);

L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
  attribution: '© OpenStreetMap contributors'
}).addTo(map);

var greenIcon = L.divIcon({
  className: '',
  html: '<div style="background-color:#1D9E75;width:14px;height:14px;border-radius:50%;border:2px solid white;box-shadow:0 0 4px rgba(0,0,0,0.4);"></div>',
  iconSize: [14, 14],
  iconAnchor: [7, 7],
  popupAnchor: [0, -10]
});

var territories = [
  {
    lat: 4.6351, lng: -74.0933,
    name: "Teusaquillo",
    desc: "High concentration of institutional invisibility. Stratum 4 households with hidden precarity."
  },
  {
    lat: 4.7167, lng: -74.0500,
    name: "Los Cedros",
    desc: "Key fieldwork territory. Mixed strata with documented hidden poverty patterns."
  },
  {
    lat: 4.6543, lng: -74.0821,
    name: "Galerías",
    desc: "High mismatch between official classification and lived experience."
  },
  {
    lat: 4.6289, lng: -74.0891,
    name: "Quinta Paredes",
    desc: "Urban walk territory. Participatory mapping fieldwork site."
  }
];

territories.forEach(function(t) {
  L.marker([t.lat, t.lng], {icon: greenIcon})
    .addTo(map)
    .bindPopup('<strong>' + t.name + '</strong><br>' + t.desc);
});
</script>
