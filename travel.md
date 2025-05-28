---
layout: default
title: Travel Diary
permalink: /travel/
---

<div class="travel-index">
    <header class="text-center mb-5">
        <h1 class="display-4">Travel Diary</h1>
        <p class="lead">Exploring the world, one destination at a time</p>
    </header>

    <div class="row">
        {% assign travel_posts = site.travel | sort: 'date' | reverse %}
        {% for post in travel_posts %}
        <div class="col-md-6 col-lg-4 mb-4">
            <div class="card h-100">
                {% if post.images.first %}
                <img src="{{ post.images.first.path | relative_url }}" 
                     class="card-img-top" 
                     alt="{{ post.title }}"
                     loading="lazy">
                {% endif %}
                <div class="card-body">
                    <h5 class="card-title">{{ post.title }}</h5>
                    <p class="text-muted">
                        <i class="fas fa-map-marker-alt me-2"></i>{{ post.location }}
                        <span class="mx-2">•</span>
                        <i class="fas fa-calendar-alt me-2"></i>{{ post.date | date: "%B %d, %Y" }}
                    </p>
                    <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
                    <a href="{{ post.url | relative_url }}" class="btn btn-outline-primary">Read More</a>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>

    <div class="travel-map mt-5">
        <h2 class="text-center mb-4">Travel Map</h2>
        <div id="map" style="height: 400px;" class="rounded"></div>
    </div>
</div>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css">

<script>
document.addEventListener('DOMContentLoaded', function() {
    // Initialize the map
    const map = L.map('map').setView([0, 0], 2);
    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
        attribution: '© OpenStreetMap contributors'
    }).addTo(map);

    // Add markers for each travel post
    {% for post in travel_posts %}
    {% if post.location %}
    fetch(`https://nominatim.openstreetmap.org/search?format=json&q={{ post.location | url_encode }}`)
        .then(response => response.json())
        .then(data => {
            if (data.length > 0) {
                const lat = parseFloat(data[0].lat);
                const lon = parseFloat(data[0].lon);
                L.marker([lat, lon])
                    .bindPopup(`
                        <strong>${post.title}</strong><br>
                        <a href="${post.url}" target="_blank">Read more</a>
                    `)
                    .addTo(map);
            }
        });
    {% endif %}
    {% endfor %}
});
</script> 