---
layout: default
title: Blog
permalink: /blog/
---

<div class="blog-index">
    <header class="text-center mb-5">
        <h1 class="display-4">Blog</h1>
        <p class="lead">Thoughts, ideas, and experiences</p>
    </header>

    <div class="row">
        {% for post in paginator.posts %}
        <div class="col-md-6 col-lg-4 mb-4">
            <div class="card h-100">
                {% if post.image %}
                <img src="{{ post.image | relative_url }}" 
                     class="card-img-top" 
                     alt="{{ post.title }}"
                     loading="lazy">
                {% endif %}
                <div class="card-body">
                    <h5 class="card-title">{{ post.title }}</h5>
                    <p class="text-muted">
                        <i class="fas fa-calendar-alt me-2"></i>{{ post.date | date: "%B %d, %Y" }}
                    </p>
                    <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
                    <a href="{{ post.url | relative_url }}" class="btn btn-outline-primary">Read More</a>
                </div>
            </div>
        </div>
        {% endfor %}
    </div>

    {% if paginator.total_pages > 1 %}
    <nav aria-label="Blog pagination" class="mt-4">
        <ul class="pagination justify-content-center">
            {% if paginator.previous_page %}
            <li class="page-item">
                <a class="page-link" href="{{ paginator.previous_page_path | relative_url }}">Previous</a>
            </li>
            {% endif %}

            {% for page in (1..paginator.total_pages) %}
            <li class="page-item {% if page == paginator.page %}active{% endif %}">
                <a class="page-link" href="{% if page == 1 %}{{ '/blog/' | relative_url }}{% else %}{{ site.paginate_path | relative_url | replace: ':num', page }}{% endif %}">
                    {{ page }}
                </a>
            </li>
            {% endfor %}

            {% if paginator.next_page %}
            <li class="page-item">
                <a class="page-link" href="{{ paginator.next_page_path | relative_url }}">Next</a>
            </li>
            {% endif %}
        </ul>
    </nav>
    {% endif %}
</div> 