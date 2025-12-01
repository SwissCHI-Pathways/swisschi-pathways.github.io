---
layout: default
title: Sponsors
description: "Partner with SwissCHI Pathways to support the next generation of HCI professionals in Switzerland."
permalink: /sponsors/
---

<div class="container">
  <div class="page-header">
    <h1>Our Sponsors</h1>
    <p class="lead">SwissCHI Pathways is made possible by the generous support of our sponsors who believe in fostering the next generation of HCI researchers and practitioners.</p>
  </div>

  <!-- Current Sponsors Section -->
  {% assign current_sponsors = "" | split: "" %}
  {% assign today = "now" | date: "%s" %}

  {% for event_data in site.data.sponsors %}
    {% assign event_key = event_data[0] %}
    {% assign event_info = event_data[1] %}
    {% assign event_date = event_info.date | date: "%s" %}
    {% if event_date >= today %}
      {% assign current_sponsors = current_sponsors | concat: event_info.sponsors %}
    {% endif %}
  {% endfor %}

  {% if current_sponsors.size > 0 %}
  <section class="sponsors-section current-sponsors-section">
    <h2>Current Sponsors</h2>
    <p class="section-intro">Supporting our upcoming events and activities.</p>

    <div class="sponsors-grid">
      {% for sponsor in current_sponsors %}
      <div class="sponsor-card">
        <a href="{{ sponsor.website }}" target="_blank" rel="noopener noreferrer" class="sponsor-link">
          <img src="{{ '/assets/images/sponsors/' | append: sponsor.logo | relative_url }}"
               alt="{{ sponsor.name }}"
               class="sponsor-logo">
          <span class="sponsor-name">{{ sponsor.name }}</span>
        </a>
        {% if sponsor.description %}
        <p class="sponsor-description">{{ sponsor.description }}</p>
        {% endif %}
      </div>
      {% endfor %}
    </div>
  </section>
  {% else %}
  <section class="sponsors-section">
    <h2>Current Sponsors</h2>
    <p class="no-sponsors">We're currently seeking sponsors for our upcoming events. <a href="{{ '/contact' | relative_url }}">Contact us</a> to learn about sponsorship opportunities.</p>
  </section>
  {% endif %}

  <!-- Previous Sponsors Section -->
  {% assign past_sponsors = "" | split: "" %}
  {% assign past_events = "" | split: "" %}

  {% for event_data in site.data.sponsors %}
    {% assign event_key = event_data[0] %}
    {% assign event_info = event_data[1] %}
    {% assign event_date = event_info.date | date: "%s" %}
    {% if event_date < today and event_info.sponsors.size > 0 %}
      {% assign past_events = past_events | push: event_info %}
    {% endif %}
  {% endfor %}

  {% if past_events.size > 0 %}
  <section class="sponsors-section previous-sponsors-section">
    <h2>Previous Sponsors</h2>
    <p class="section-intro">We're grateful to all organizations that have supported SwissCHI Pathways.</p>

    {% for event in past_events reversed %}
    <div class="past-event-sponsors">
      <h3 class="past-event-title">{{ event.name }} <span class="event-year">({{ event.date | date: "%B %Y" }})</span></h3>
      <div class="previous-sponsors-grid">
        {% for sponsor in event.sponsors %}
        <div class="previous-sponsor-item">
          <a href="{{ sponsor.website }}" target="_blank" rel="noopener noreferrer">
            <img src="{{ '/assets/images/sponsors/' | append: sponsor.logo | relative_url }}"
                 alt="{{ sponsor.name }}"
                 class="previous-sponsor-logo">
          </a>
          <span class="previous-sponsor-name">{{ sponsor.name }}</span>
        </div>
        {% endfor %}
      </div>
    </div>
    {% endfor %}
  </section>
  {% endif %}

  <!-- Become a Sponsor CTA -->
  <section class="become-sponsor-section">
    <div class="cta-card">
      <h2>Become a Sponsor</h2>
      <p>Support the next generation of HCI researchers and practitioners. Sponsorship opportunities include event support, networking events, and visibility across our community.</p>
      <a href="{{ '/contact' | relative_url }}" class="btn btn-primary">Get in Touch</a>
    </div>
  </section>
</div>

<style>
  .page-header {
    margin-bottom: 3rem;
  }

  .page-header h1:after {
    margin: 0.5rem 0 1rem;
  }

  .lead {
    font-size: 1.2rem;
    color: #4b5563;
    max-width: 800px;
  }

  .sponsors-section {
    margin-bottom: 4rem;
  }

  .sponsors-section h2 {
    color: #3C2FB3;
    margin-bottom: 0.75rem;
    font-size: 2rem;
  }

  .section-intro {
    color: #6b7280;
    font-size: 1.1rem;
    margin-bottom: 2rem;
  }

  .no-sponsors {
    color: #6b7280;
    font-size: 1.05rem;
  }

  .no-sponsors a {
    color: #3C2FB3;
    text-decoration: underline;
  }

  /* Sponsors Grid */
  .sponsors-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
  }

  .sponsor-card {
    text-align: center;
    padding: 2rem;
    background: white;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    border: 2px solid #e5e7eb;
  }

  .sponsor-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.12);
    border-color: #3C2FB3;
  }

  .sponsor-link {
    text-decoration: none;
    color: inherit;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  .sponsor-logo {
    max-width: 100%;
    height: auto;
    max-height: 100px;
    object-fit: contain;
  }

  .sponsor-name {
    font-weight: 600;
    color: #1f2937;
    font-size: 1.1rem;
  }

  .sponsor-description {
    margin-top: 0.5rem;
    color: #6b7280;
    font-size: 0.9rem;
    line-height: 1.5;
  }

  /* Previous Sponsors Styles */
  .previous-sponsors-section {
    background-color: #f9fafb;
    padding: 2rem;
    border-radius: 12px;
  }

  .past-event-sponsors {
    margin-bottom: 2.5rem;
  }

  .past-event-sponsors:last-child {
    margin-bottom: 0;
  }

  .past-event-title {
    color: #1f2937;
    font-size: 1.3rem;
    margin-bottom: 1.25rem;
    font-weight: 600;
  }

  .event-year {
    color: #9ca3af;
    font-weight: 400;
    font-size: 1rem;
  }

  .previous-sponsors-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
    gap: 1.5rem;
  }

  .previous-sponsor-item {
    text-align: center;
    padding: 1.25rem;
    background: white;
    border-radius: 8px;
    border: 1px solid #e5e7eb;
    transition: opacity 0.3s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.75rem;
  }

  .previous-sponsor-item:hover {
    opacity: 0.8;
  }

  .previous-sponsor-logo {
    max-width: 100%;
    height: auto;
    max-height: 70px;
    object-fit: contain;
    filter: grayscale(20%);
    opacity: 0.9;
  }

  .previous-sponsor-name {
    font-size: 0.9rem;
    font-weight: 600;
    color: #4b5563;
  }

  /* Become a Sponsor Section */
  .become-sponsor-section {
    margin-top: 4rem;
  }

  .cta-card {
    background: linear-gradient(135deg, #3C2FB3 0%, #5B4CC7 100%);
    color: white;
    padding: 3rem;
    border-radius: 12px;
    text-align: center;
    box-shadow: 0 10px 25px rgba(60, 47, 179, 0.2);
  }

  .cta-card h2 {
    color: white;
    margin-bottom: 1rem;
    font-size: 2rem;
  }

  .cta-card p {
    font-size: 1.1rem;
    margin-bottom: 2rem;
    opacity: 0.95;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
  }

  .cta-card .btn-primary {
    background-color: white;
    color: #3C2FB3;
    border: none;
    font-weight: 600;
    padding: 0.875rem 2rem;
  }

  .cta-card .btn-primary:hover {
    background-color: #f3f4f6;
    transform: translateY(-2px);
  }

  /* Responsive Design */
  @media (max-width: 768px) {
    .sponsors-grid {
      grid-template-columns: 1fr;
    }

    .previous-sponsors-grid {
      grid-template-columns: repeat(2, 1fr);
    }

    .cta-card {
      padding: 2rem;
    }

    .cta-card h2 {
      font-size: 1.5rem;
    }

    .cta-card p {
      font-size: 1rem;
    }
  }
</style>
