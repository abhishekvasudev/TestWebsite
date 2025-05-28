---
layout: default
title: Contact
permalink: /contact/
---

<div class="contact-page">
    <header class="text-center mb-5">
        <h1 class="display-4">Contact</h1>
        <p class="lead">Get in touch with me</p>
    </header>

    <div class="row justify-content-center">
        <div class="col-md-8">
            <div class="card">
                <div class="card-body">
                    <form id="contact-form" action="https://formspree.io/f/abhishekvasudev7@gmail.com" method="POST">
                        <div class="mb-3">
                            <label for="name" class="form-label">Name</label>
                            <input type="text" class="form-control" id="name" name="name" required>
                        </div>
                        <div class="mb-3">
                            <label for="email" class="form-label">Email</label>
                            <input type="email" class="form-control" id="email" name="email" required>
                        </div>
                        <div class="mb-3">
                            <label for="message" class="form-label">Message</label>
                            <textarea class="form-control" id="message" name="message" rows="5" required></textarea>
                        </div>
                        <button type="submit" class="btn btn-primary">Send Message</button>
                    </form>
                </div>
            </div>

            <div class="card mt-4">
                <div class="card-body">
                    <h5 class="card-title">Other Ways to Connect</h5>
                    <div class="list-group">
                        <a href="mailto:abhishekvasudev7@gmail.com" class="list-group-item list-group-item-action">
                            <i class="fas fa-envelope fa-fw me-2"></i>
                            contact@abhishekvasu.dev
                        </a>
                        <a href="https://www.linkedin.com/in/abhishek-vasudev/" class="list-group-item list-group-item-action">
                            <i class="fab fa-linkedin fa-fw me-2"></i>
                            LinkedIn
                        </a>
                        <a href="https://x.com/abhishekvasude1" class="list-group-item list-group-item-action">
                            <i class="fab fa-twitter fa-fw me-2"></i>
                            Twitter
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

<script>
document.getElementById('contact-form').addEventListener('submit', function(e) {
    e.preventDefault();
    const form = e.target;
    const submitButton = form.querySelector('button[type="submit"]');
    const originalText = submitButton.innerHTML;
    
    submitButton.disabled = true;
    submitButton.innerHTML = '<span class="spinner-border spinner-border-sm" role="status" aria-hidden="true"></span> Sending...';
    
    fetch(form.action, {
        method: 'POST',
        body: new FormData(form),
        headers: {
            'Accept': 'application/json'
        }
    })
    .then(response => {
        if (response.ok) {
            alert('Message sent successfully!');
            form.reset();
        } else {
            throw new Error('Network response was not ok');
        }
    })
    .catch(error => {
        alert('There was a problem sending your message. Please try again.');
    })
    .finally(() => {
        submitButton.disabled = false;
        submitButton.innerHTML = originalText;
    });
});
</script> 