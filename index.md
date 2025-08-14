---
layout: default
title: "Welcome to The Taj Tours"
---

<section class="container my-5">
  <div class="row align-items-center mb-4">
    <div class="col-lg-7">
      <h1 class="display-5 fw-bold">Discover India, one unforgettable journey at a time.</h1>
      <p class="lead">Handcrafted trips, detailed itineraries, and local insights—made simple with Markdown. Add or edit tours in <code>_tours/</code> and publish instantly via GitHub Pages.</p>
      <a class="btn btn-primary btn-lg" href="#tours">Explore Tours</a>
    </div>
    <div class="col-lg-5 text-center mt-4 mt-lg-0">
      <img src="{{ '/assets/images/hero.svg' | relative_url }}" alt="The Taj Tours" class="img-fluid">
    </div>
  </div>

  <hr class="my-5">

  <h2 id="tours" class="mb-4">Popular Tours</h2>
  <div class="row g-4">
    {% assign sorted = site.tours | sort: 'date' | reverse %}
    {% for tour in sorted %}
    <div class="col-md-6 col-lg-4">
      <div class="card h-100 shadow-sm">
        {% if tour.image %}
        <img src="{{ tour.image | relative_url }}" class="card-img-top" alt="{{ tour.title }}">
        {% endif %}
        <div class="card-body d-flex flex-column">
          <h5 class="card-title">{{ tour.title }}</h5>
          <p class="card-text mb-2"><strong>Location:</strong> {{ tour.location }}</p>
          <p class="card-text"><strong>Duration:</strong> {{ tour.days }} days</p>
          <div class="mt-auto d-grid">
            <a href="{{ tour.url | relative_url }}" class="btn btn-outline-primary">View Itinerary</a>
          </div>
        </div>
        <div class="card-footer bg-white">
          <small class="text-muted"><strong>Price:</strong> {{ tour.price }}</small>
        </div>
      </div>
    </div>
    {% endfor %}
  </div>
</section>
