---
layout: default
title: Interesting Links
permalink: /links/
---

<div class="container py-5">
    <h1 class="display-4 mb-5">Interesting Links</h1>
    
    <div class="row">
        <div class="col-lg-8">
            {% for link in site.links %}
            <article class="card mb-4">
                <div class="card-body">
                    <h2 class="card-title h4">
                        <a href="{{ link.url | relative_url }}" class="text-decoration-none">{{ link.link_title }}</a>
                    </h2>
                    <p class="text-muted mb-3">
                        <i class="fas fa-calendar-alt"></i> {{ link.date | date: "%B %d, %Y" }}
                    </p>
                    <p class="card-text">{{ link.link_description }}</p>
                    <div class="d-flex gap-2 mb-3">
                        {% for tag in link.tags %}
                        <span class="badge bg-primary">{{ tag }}</span>
                        {% endfor %}
                    </div>
                    <div class="d-flex gap-2">
                        <a href="{{ link.url | relative_url }}" class="btn btn-outline-primary">Read More</a>
                        <a href="{{ link.link_url }}" class="btn btn-primary" target="_blank" rel="noopener">
                            <i class="fas fa-external-link-alt"></i> Visit Link
                        </a>
                    </div>
                </div>
            </article>
            {% endfor %}
        </div>
        
        <div class="col-lg-4">
            <div class="card mb-4">
                <div class="card-body">
                    <h5 class="card-title">Categories</h5>
                    <div class="d-flex flex-wrap gap-2">
                        {% assign tags = site.links | map: "tags" | uniq %}
                        {% for tag in tags %}
                        <a href="{{ '/tag/' | append: tag | relative_url }}" class="badge bg-secondary text-decoration-none">
                            {{ tag }}
                        </a>
                        {% endfor %}
                    </div>
                </div>
            </div>
            
            <div class="card">
                <div class="card-body">
                    <h5 class="card-title">About This Section</h5>
                    <p class="card-text">
                        This is where I share interesting articles, videos, and resources that I've come across and found valuable. 
                        Each link includes my thoughts on why I found it interesting and what I learned from it.
                    </p>
                </div>
            </div>
        </div>
    </div>
</div> 