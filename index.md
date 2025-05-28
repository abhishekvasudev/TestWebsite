---
layout: default
title: Home
---

<section class="hero">
    <div class="container">
        <div class="row align-items-center">
            <div class="col-lg-6">
                <h1>Hi, I'm Abhishek Vasudev</h1>
                <p class="lead">Software Engineer & Tech Enthusiast</p>
                <p>I build modern web applications and share my experiences through writing.</p>
                <div class="mt-4">
                    <a href="/blog" class="btn btn-primary me-2">Read Blog</a>
                    <a href="/contact" class="btn btn-outline-primary">Get in Touch</a>
                </div>
            </div>
            <div class="col-lg-6">
                <img src="/assets/images/profile.jpg" alt="Abhishek Vasudev" class="img-fluid rounded-circle" loading="lazy">
            </div>
        </div>
    </div>
</section>

<section class="py-5">
    <div class="container">
        <h2 class="text-center mb-4">Recent Projects</h2>
        <div class="row">
            {% for project in site.data.projects limit:3 %}
            <div class="col-md-4 mb-4">
                <div class="card h-100">
                    <img src="{{ project.image }}" class="card-img-top" alt="{{ project.title }}" loading="lazy">
                    <div class="card-body">
                        <h5 class="card-title">{{ project.title }}</h5>
                        <p class="card-text">{{ project.description }}</p>
                        <a href="{{ project.url }}" class="btn btn-outline-primary" target="_blank">View Project</a>
                    </div>
                </div>
            </div>
            {% endfor %}
        </div>
    </div>
</section>

<section class="py-5 bg-light">
    <div class="container">
        <h2 class="text-center mb-4">Latest Blog Posts</h2>
        <div class="row">
            {% for post in site.posts limit:3 %}
            <div class="col-md-4 mb-4">
                <div class="card h-100">
                    <div class="card-body">
                        <h5 class="card-title">{{ post.title }}</h5>
                        <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
                        <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
                        <a href="{{ post.url }}" class="btn btn-link">Read More</a>
                    </div>
                </div>
            </div>
            {% endfor %}
        </div>
        <div class="text-center mt-4">
            <a href="/blog" class="btn btn-primary">View All Posts</a>
        </div>
    </div>
</section>

<section class="py-5">
    <div class="container">
        <h2 class="text-center mb-4">Skills & Expertise</h2>
        <div class="row">
            <div class="col-md-4 mb-4">
                <div class="card h-100">
                    <div class="card-body text-center">
                        <i class="fas fa-code fa-3x mb-3 text-primary"></i>
                        <h5 class="card-title">Web Development</h5>
                        <p class="card-text">Full-stack development with modern frameworks and best practices.</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4 mb-4">
                <div class="card h-100">
                    <div class="card-body text-center">
                        <i class="fas fa-mobile-alt fa-3x mb-3 text-primary"></i>
                        <h5 class="card-title">Mobile Development</h5>
                        <p class="card-text">Cross-platform mobile app development with React Native.</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4 mb-4">
                <div class="card h-100">
                    <div class="card-body text-center">
                        <i class="fas fa-cloud fa-3x mb-3 text-primary"></i>
                        <h5 class="card-title">Cloud & DevOps</h5>
                        <p class="card-text">Cloud architecture and CI/CD pipeline implementation.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</section> 