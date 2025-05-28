---
layout: default
title: Home
---

<div class="hero">
    <div class="container">
        <div class="row align-items-center">
            <div class="col-lg-6">
                <h1 class="display-4">Hi, I'm Abhishek Vasudev</h1>
                <p class="lead">Software Engineer & Tech Enthusiast</p>
                <div class="mt-4">
                    <a href="https://github.com/abhishekvasudev" target="_blank" rel="noopener" class="btn btn-light btn-lg me-3">
                        <i class="fab fa-github"></i> GitHub
                    </a>
                    <a href="https://www.linkedin.com/in/abhishek-vasudev/" target="_blank" rel="noopener" class="btn btn-light btn-lg me-3">
                        <i class="fab fa-linkedin"></i> LinkedIn
                    </a>
                    <a href="https://x.com/abhishekvasude1" target="_blank" rel="noopener" class="btn btn-light btn-lg">
                        <svg viewBox="0 0 24 24" width="16" height="16" fill="currentColor" style="margin-right: 4px;">
                            <path d="M18.244 2.25h3.308l-7.227 8.26 8.502 11.24H16.17l-5.214-6.817L4.99 21.75H1.68l7.73-8.835L1.254 2.25H8.08l4.713 6.231zm-1.161 17.52h1.833L7.084 4.126H5.117z"/>
                        </svg>
                        X
                    </a>
                </div>
            </div>
            <div class="col-lg-6 d-none d-lg-block">
                <img src="{{ '/assets/images/profile.jpg' | relative_url }}" alt="Abhishek Vasudev" class="img-fluid rounded-circle">
            </div>
        </div>
    </div>
</div>

<section class="py-5">
    <div class="container">
        <h2 class="text-center mb-5">Skills & Expertise</h2>
        <div class="row g-4">
            <div class="col-md-4">
                <div class="card h-100">
                    <div class="card-body">
                        <i class="fas fa-code fa-2x text-primary mb-3"></i>
                        <h5 class="card-title">Web Development</h5>
                        <p class="card-text">Full-stack development with modern frameworks and best practices.</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card h-100">
                    <div class="card-body">
                        <i class="fas fa-mobile-alt fa-2x text-primary mb-3"></i>
                        <h5 class="card-title">Mobile Development</h5>
                        <p class="card-text">Native and cross-platform mobile app development.</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card h-100">
                    <div class="card-body">
                        <i class="fas fa-cloud fa-2x text-primary mb-3"></i>
                        <h5 class="card-title">Cloud & DevOps</h5>
                        <p class="card-text">Cloud architecture and CI/CD pipeline implementation.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section>

<section class="py-5 bg-light">
    <div class="container">
        <h2 class="text-center mb-5">Recent Projects</h2>
        <div class="row g-4">
            {% for project in site.data.projects limit:3 %}
            <div class="col-md-4">
                <div class="card h-100">
                    {% if project.image %}
                    <img src="{{ project.image | relative_url }}" class="card-img-top" alt="{{ project.title }}">
                    {% endif %}
                    <div class="card-body">
                        <h5 class="card-title">{{ project.title }}</h5>
                        <p class="card-text">{{ project.description }}</p>
                        <div class="d-flex gap-2">
                            {% for tech in project.technologies %}
                            <span class="badge bg-primary">{{ tech }}</span>
                            {% endfor %}
                        </div>
                    </div>
                    <div class="card-footer bg-transparent border-0">
                        <a href="{{ project.url }}" class="btn btn-outline-primary" target="_blank">View Project</a>
                    </div>
                </div>
            </div>
            {% endfor %}
        </div>
    </div>
</section>

<section class="py-5">
    <div class="container">
        <h2 class="text-center mb-5">Latest Blog Posts</h2>
        <div class="row g-4">
            {% for post in site.posts limit:3 %}
            <div class="col-md-4">
                <div class="card h-100">
                    {% if post.image %}
                    <img src="{{ post.image | relative_url }}" class="card-img-top" alt="{{ post.title }}">
                    {% endif %}
                    <div class="card-body">
                        <h5 class="card-title">{{ post.title }}</h5>
                        <p class="post-meta">
                            <i class="fas fa-calendar-alt"></i>{{ post.date | date: "%B %d, %Y" }}
                        </p>
                        <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
                    </div>
                    <div class="card-footer bg-transparent border-0">
                        <a href="{{ post.url | relative_url }}" class="btn btn-outline-primary">Read More</a>
                    </div>
                </div>
            </div>
            {% endfor %}
        </div>
        <div class="text-center mt-4">
            <a href="{{ '/blog' | relative_url }}" class="btn btn-primary">View All Posts</a>
        </div>
    </div>
</section> 