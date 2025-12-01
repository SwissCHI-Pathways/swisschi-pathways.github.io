---
layout: default
title: Events
description: "Join SwissCHI Pathways workshops, lectures, and networking events for HCI students in Switzerland."
---

<div class="container">
  <div class="page-header">
    <h1>Upcoming Events</h1>
    <p class="lead">Join us for workshops, lectures, and networking events to enhance your HCI knowledge and connect with peers.</p>
  </div>
  
  <div class="events-list">
    {% assign today = "now" | date: "%s" %}
    {% assign upcoming_events = "" | split: "" %}

    {% for event in site.data.events %}
      {% assign event_date = event.date | date: "%s" %}
      {% if event_date >= today %}
        {% assign upcoming_events = upcoming_events | push: event %}
      {% endif %}
    {% endfor %}

    {% if upcoming_events.size > 0 %}
      {% for event in upcoming_events %}
      <!-- Event Schema.org structured data -->
      <script type="application/ld+json">
      {
        "@context": "https://schema.org",
        "@type": "Event",
        "name": "{{ event.title }}",
        "description": "{{ event.description | strip_html | escape }}",
        "startDate": "{{ event.date }}T{{ event.time | split: ' - ' | first | replace: ':', '' | slice: 0, 2 }}:{{ event.time | split: ' - ' | first | slice: 3, 2 }}:00",
        "location": {
          "@type": "Place",
          "name": "{{ event.location }}",
          "address": "{{ event.location }}"
        },
        "organizer": {
          "@type": "Organization",
          "name": "SwissCHI Pathways",
          "url": "{{ site.url }}"
        }
        {% if event.registration_url %}
        ,"eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
        "eventStatus": "https://schema.org/EventScheduled"
        {% endif %}
      }
      </script>
      <div class="event-card">
        <div class="event-date-badge">
          <span class="month">{{ event.date | date: "%b" | upcase }}</span>
          <span class="day">{{ event.date | date: "%-d" }}</span>
          <span class="year">{{ event.date | date: "%Y" }}</span>
        </div>
        <div class="event-content">
          <h3>{{ event.title }}</h3>
          {% if event.subtitle %}
          <h5><span class="text-muted">{{ event.subtitle }}</span></h5>
          {% endif %}

          <!-- Event Sponsors (near title) -->
          {% assign event_sponsors = site.data.sponsors[event.slug] %}
          {% if event_sponsors and event_sponsors.sponsors.size > 0 %}
          <div class="event-sponsors-inline">
            <span class="sponsor-label">Sponsored by</span>
            <div class="sponsors-inline-grid">
              {% for sponsor in event_sponsors.sponsors %}
              <a href="{{ sponsor.website }}" target="_blank" rel="noopener noreferrer" class="sponsor-inline-link" title="{{ sponsor.name }}">
                <img src="{{ '/assets/images/sponsors/' | append: sponsor.logo | relative_url }}"
                     alt="{{ sponsor.name }}"
                     class="sponsor-inline-logo">
              </a>
              {% endfor %}
            </div>
          </div>
          {% endif %}

          <p>{{ event.description }}</p>

          {% if event.schedule %}
          <div class="event-schedule">
            <h4>Schedule</h4>
            {% for item in event.schedule %}
            <div class="schedule-item {% if item.is_featured %}schedule-item-featured{% endif %}">
              <strong>{{ item.time }} | {{ item.title }}</strong>

              {% if item.speaker %}
              <div class="speaker-section">
                <div class="speaker-header">
                  {% if item.speaker.photo %}
                  <div class="speaker-photo">
                    <img src="{{ '/assets/images/speakers/' | append: item.speaker.photo | relative_url }}" alt="{{ item.speaker.name }}" />
                  </div>
                  {% endif %}
                  <div class="speaker-info-wrapper">
                    <div class="speaker-details">
                      <span class="speaker-name">{{ item.speaker.name }}</span>
                      <span class="speaker-position">{{ item.speaker.position }} @ {{ item.speaker.organization }}</span>
                    </div>
                    <div class="speaker-links">
                    {% if item.speaker.website %}
                    <a href="{{ item.speaker.website }}" target="_blank" rel="noopener noreferrer" class="speaker-link" title="Website">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M4.715 6.542 3.343 7.914a3 3 0 1 0 4.243 4.243l1.828-1.829A3 3 0 0 0 8.586 5.5L8 6.086a1.002 1.002 0 0 0-.154.199 2 2 0 0 1 .861 3.337L6.88 11.45a2 2 0 1 1-2.83-2.83l.793-.792a4.018 4.018 0 0 1-.128-1.287z"/>
                        <path d="M6.586 4.672A3 3 0 0 0 7.414 9.5l.775-.776a2 2 0 0 1-.896-3.346L9.12 3.55a2 2 0 1 1 2.83 2.83l-.793.792c.112.42.155.855.128 1.287l1.372-1.372a3 3 0 1 0-4.243-4.243L6.586 4.672z"/>
                      </svg>
                    </a>
                    {% endif %}
                    {% if item.speaker.linkedin %}
                    <a href="{{ item.speaker.linkedin }}" target="_blank" rel="noopener noreferrer" class="speaker-link" title="LinkedIn">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854V1.146zm4.943 12.248V6.169H2.542v7.225h2.401zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248-.822 0-1.359.54-1.359 1.248 0 .694.521 1.248 1.327 1.248h.016zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016a5.54 5.54 0 0 1 .016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225h2.4z"/>
                      </svg>
                    </a>
                    {% endif %}
                    {% if item.speaker.email %}
                    <a href="mailto:{{ item.speaker.email }}" class="speaker-link" title="Email">
                      <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M0 4a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V4Zm2-1a1 1 0 0 0-1 1v.217l7 4.2 7-4.2V4a1 1 0 0 0-1-1H2Zm13 2.383-4.708 2.825L15 11.105V5.383Zm-.034 6.876-5.64-3.471L8 9.583l-1.326-.795-5.64 3.47A1 1 0 0 0 2 13h12a1 1 0 0 0 .966-.741ZM1 11.105l4.708-2.897L1 5.383v5.722Z"/>
                      </svg>
                    </a>
                    {% endif %}
                    </div>
                  </div>
                </div>

                {% if item.speaker.talk_title %}
                <div class="talk-title">
                  <h5>{{ item.speaker.talk_title }}</h5>
                </div>
                {% endif %}

                {% if item.speaker.abstract %}
                <div class="speaker-abstract">
                  <h6>Abstract</h6>
                  <p>{{ item.speaker.abstract }}</p>
                </div>
                {% endif %}

                {% if item.speaker.bio %}
                <div class="speaker-bio">
                  <h6>About the Speaker</h6>
                  <p>{{ item.speaker.bio }}</p>
                </div>
                {% endif %}
              </div>
              {% endif %}

              {% if item.description %}
              <p>{{ item.description }}</p>
              {% endif %}
              {% if item.list %}
              <ul>
                {% for list_item in item.list %}
                <li>{{ list_item }}</li>
                {% endfor %}
              </ul>
              {% endif %}
              {% if item.details %}
                {% for detail in item.details %}
                <p>{{ detail }}</p>
                {% endfor %}
              {% endif %}
            </div>
            {% endfor %}
          </div>
          {% endif %}

          <div class="event-details">
            {% if event.location %}
            <div class="event-detail">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16" aria-hidden="true">
                <path d="M8 16s6-5.686 6-10A6 6 0 0 0 2 6c0 4.314 6 10 6 10zm0-7a3 3 0 1 1 0-6 3 3 0 0 1 0 6z"/>
              </svg>
              <span>{{ event.location }}</span>
            </div>
            {% endif %}
            {% if event.time %}
            <div class="event-detail">
              <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16" aria-hidden="true">
                <path d="M8 3.5a.5.5 0 0 0-1 0V9a.5.5 0 0 0 .252.434l3.5 2a.5.5 0 0 0 .496-.868L8 8.71V3.5z"/>
                <path d="M8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16zm7-8A7 7 0 1 1 1 8a7 7 0 0 1 14 0z"/>
              </svg>
              <span>{{ event.time }}</span>
            </div>
            {% endif %}
          </div>
          {% if event.registration_url %}
          <a href="{{ event.registration_url }}" target="_blank" class="btn btn-primary">Register</a>
          {% endif %}
        </div>
      </div>
      {% endfor %}
    {% else %}
      <div class="coming-soon-card">
        <div class="coming-soon-icon">
          <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="currentColor" viewBox="0 0 16 16">
            <path d="M3.5 0a.5.5 0 0 1 .5.5V1h8V.5a.5.5 0 0 1 1 0V1h1a2 2 0 0 1 2 2v11a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2V3a2 2 0 0 1 2-2h1V.5a.5.5 0 0 1 .5-.5zM1 4v10a1 1 0 0 0 1 1h12a1 1 0 0 0 1-1V4H1z"/>
            <path d="M8 7.5a.5.5 0 0 0-1 0V9H5.5a.5.5 0 0 0 0 1H7v1.5a.5.5 0 0 0 1 0V10h1.5a.5.5 0 0 0 0-1H8V7.5z"/>
          </svg>
        </div>
        <h3>We're brewing up new events!</h3>
        <p>Check back soon or get in touch to stay updated on upcoming SwissCHI Pathways activities.</p>
        <a href="{{ '/contact' | relative_url }}" class="btn btn-primary">Contact Us</a>
      </div>
    {% endif %}
  </div>

  <h2>Past Events</h2>

  {% assign past_events = "" | split: "" %}
  {% for event in site.data.events %}
    {% assign event_date = event.date | date: "%s" %}
    {% if event_date < today %}
      {% assign past_events = past_events | push: event %}
    {% endif %}
  {% endfor %}

  {% if past_events.size > 0 %}
  <div class="past-events-list">
    {% for event in past_events reversed %}
    <div class="past-event-card">
      <div class="past-event-header">
        <h3>{{ event.title }}</h3>
        <span class="past-event-date">{{ event.date | date: "%B %-d, %Y" }}</span>
      </div>
      {% if event.subtitle %}
      <p class="past-event-subtitle">{{ event.subtitle }}</p>
      {% endif %}
      <p>{{ event.description }}</p>
      {% if event.location %}
      <p class="past-event-location">📍 {{ event.location }}</p>
      {% endif %}

      {% comment %} Speakers from schedule {% endcomment %}
      {% assign speakers = "" | split: "" %}
      {% for item in event.schedule %}
        {% if item.speaker %}
          {% assign speakers = speakers | push: item.speaker %}
        {% endif %}
      {% endfor %}
      {% if speakers.size > 0 %}
      <div class="past-event-speakers">
        <span class="past-event-label">Featured speaker{% if speakers.size > 1 %}s{% endif %}:</span>
        <div class="past-speakers-list">
          {% for speaker in speakers %}
          <div class="past-speaker">
            {% if speaker.photo %}
            <img src="{{ '/assets/images/speakers/' | append: speaker.photo | relative_url }}" alt="{{ speaker.name }}" class="past-speaker-photo">
            {% endif %}
            <div class="past-speaker-info">
              <span class="past-speaker-name">{{ speaker.name }}</span>
              <span class="past-speaker-role">{{ speaker.position }}, {{ speaker.organization }}</span>
            </div>
          </div>
          {% endfor %}
        </div>
      </div>
      {% endif %}

      {% comment %} Sponsors {% endcomment %}
      {% assign event_sponsors = site.data.sponsors[event.slug] %}
      {% if event_sponsors and event_sponsors.sponsors.size > 0 %}
      <div class="past-event-sponsors">
        <span class="past-event-label">Sponsored by:</span>
        <div class="past-sponsors-list">
          {% for sponsor in event_sponsors.sponsors %}
          <a href="{{ sponsor.website }}" target="_blank" rel="noopener noreferrer" class="past-sponsor-link" title="{{ sponsor.name }}">
            <img src="{{ '/assets/images/sponsors/' | append: sponsor.logo | relative_url }}" alt="{{ sponsor.name }}" class="past-sponsor-logo">
          </a>
          {% endfor %}
        </div>
      </div>
      {% endif %}
    </div>
    {% endfor %}
  </div>
  {% else %}
  <p>No past events yet. Stay tuned for our upcoming launch!</p>
  {% endif %}

  <div class="subscribe-events mt-3">
    <h3>Stay Updated</h3>
    <p>Don't miss out on our upcoming events. Get in touch with us to stay informed about SwissCHI Pathways activities.</p>
    <a href="{{ '/contact' | relative_url }}" class="btn btn-primary">Contact Us</a>
    <a href="{{ '/team' | relative_url }}" class="btn btn-outline">Meet the Organizers</a>
  </div>
</div>

<style>
  .page-header {
    margin-bottom: 2.5rem;
  }
  
  .page-header h1:after {
    margin: 0.5rem 0 1rem;
  }
  
  .lead {
    font-size: 1.2rem;
    color: #4b5563;
  }
  
  .events-list {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;
    margin: 2.5rem 0;
  }
  
  .event-card {
    display: flex;
    border: 1px solid #e5e7eb;
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    overflow: hidden;
  }
  
  .event-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
  }
  
  .event-date-badge {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #3C2FB3;
    color: white;
    padding: 1rem;
    min-width: 90px;
    text-align: center;
  }
  
  .event-date-badge .month {
    font-size: 1rem;
    font-weight: 700;
    text-transform: uppercase;
  }
  
  .event-date-badge .day {
    font-size: 2rem;
    font-weight: 700;
    line-height: 1;
    margin: 0.25rem 0;
  }
  
  .event-date-badge .year {
    font-size: 0.9rem;
    opacity: 0.8;
  }
  
  .event-content {
    padding: 1.5rem;
    flex: 1;
  }
  
  .event-content h3 {
    margin-bottom: 0.75rem;
    color: #3C2FB3;
  }

  .event-content h5 {
    margin-top: -0.5rem;
    margin-bottom: 1rem;
    color: #3C2FB3;
    font-weight: 400;
  }

  .event-schedule {
    background-color: #f9fafb;
    padding: 1.5rem;
    border-radius: 8px;
    margin: 1.5rem 0;
  }

  .event-schedule h4 {
    margin-top: 0;
    margin-bottom: 1.25rem;
    color: #3C2FB3;
    font-size: 1.25rem;
  }

  .schedule-item {
    margin-bottom: 1.25rem;
    padding-bottom: 1.25rem;
    border-bottom: 1px solid #e5e7eb;
  }

  .schedule-item:last-child {
    margin-bottom: 0;
    padding-bottom: 0;
    border-bottom: none;
  }

  .schedule-item strong {
    display: block;
    color: #1f2937;
    margin-bottom: 0.5rem;
    font-size: 1.05rem;
  }

  .schedule-item p {
    margin: 0.25rem 0;
    color: #4b5563;
    line-height: 1.6;
  }

  .schedule-item ul {
    margin: 0.5rem 0 0.5rem 1.5rem;
    color: #4b5563;
  }

  .schedule-item li {
    margin: 0.25rem 0;
  }

  /* Featured Schedule Item (Guest Talk) */
  .schedule-item-featured {
    background: linear-gradient(135deg, #f0edff 0%, #f8f6ff 100%);
    border-left: 4px solid #3C2FB3;
    padding: 1.5rem !important;
    margin: 1.5rem -0.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(60, 47, 179, 0.1);
  }

  .schedule-item-featured strong {
    color: #3C2FB3;
    font-size: 1.1rem;
  }

  /* Speaker Section */
  .speaker-section {
    margin: 1.5rem 0;
  }

  .speaker-header {
    display: flex;
    gap: 1.5rem;
    align-items: center;
    margin-bottom: 1.5rem;
    padding: 1.5rem;
    background-color: white;
    border-radius: 8px;
    border: 1px solid #e5e7eb;
  }

  .speaker-photo {
    flex-shrink: 0;
  }

  .speaker-photo img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid #3C2FB3;
  }

  .speaker-info-wrapper {
    flex: 1;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 1rem;
  }

  .speaker-details {
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }

  .speaker-name {
    font-weight: 700;
    color: #1f2937;
    font-size: 1.05rem;
  }

  .speaker-position {
    color: #6b7280;
    font-size: 0.9rem;
  }

  .speaker-links {
    display: flex;
    gap: 0.75rem;
  }

  .speaker-link {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    background-color: #f3f4f6;
    border-radius: 50%;
    color: #3C2FB3;
    transition: all 0.3s ease;
    text-decoration: none;
  }

  .speaker-link:hover {
    background-color: #3C2FB3;
    color: white;
    transform: scale(1.1);
  }

  .speaker-link svg {
    display: block;
  }

  /* Talk Title */
  .talk-title {
    margin: 1.25rem 0;
    padding-left: 0.5rem;
    border-left: 3px solid #3C2FB3;
  }

  .talk-title h5 {
    margin: 0;
    color: #1f2937;
    font-size: 1.1rem;
    font-weight: 600;
    line-height: 1.4;
  }

  /* Speaker Abstract */
  .speaker-abstract {
    margin: 1.25rem 0;
    padding: 1rem;
    background-color: rgba(60, 47, 179, 0.03);
    border-radius: 6px;
  }

  .speaker-abstract h6 {
    margin: 0 0 0.75rem 0;
    color: #3C2FB3;
    font-size: 0.9rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .speaker-abstract p {
    margin: 0;
    color: #374151;
    line-height: 1.7;
    font-size: 0.95rem;
  }

  /* Speaker Bio */
  .speaker-bio {
    margin: 1.25rem 0;
    padding: 1rem;
    background-color: #f9fafb;
    border-radius: 6px;
  }

  .speaker-bio h6 {
    margin: 0 0 0.75rem 0;
    color: #3C2FB3;
    font-size: 0.9rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }

  .speaker-bio p {
    margin: 0;
    color: #4b5563;
    line-height: 1.7;
    font-size: 0.95rem;
  }

  @media (max-width: 640px) {
    .speaker-header {
      flex-direction: column;
      align-items: center;
      text-align: center;
      gap: 1rem;
    }

    .speaker-info-wrapper {
      flex-direction: column;
      align-items: center;
      text-align: center;
    }

    .speaker-photo img {
      width: 80px;
      height: 80px;
    }

    .schedule-item-featured {
      margin-left: 0;
      margin-right: 0;
    }

    .talk-title h5 {
      font-size: 1rem;
    }
  }

  .event-details {
    margin: 1.5rem 0;
  }
  
  .event-detail {
    display: flex;
    align-items: center;
    margin-bottom: 0.5rem;
    color: #4b5563;
  }
  
  .event-detail svg {
    margin-right: 0.5rem;
    color: #3C2FB3;
  }
  
  .subscribe-events {
    background-color: #f3f4f6;
    padding: 2rem;
    border-radius: 12px;
    margin-top: 3rem;
    text-align: center;
  }

  .subscribe-events h3 {
    margin-bottom: 0.75rem;
  }

  .subscribe-events p {
    margin-bottom: 1.5rem;
    color: #4b5563;
  }

  .subscribe-events .btn {
    display: inline-block;
  }
  
  @media (max-width: 640px) {
    .event-card {
      flex-direction: column;
    }
    
    .event-date-badge {
      flex-direction: row;
      gap: 0.5rem;
      padding: 0.75rem;
    }
    
    .event-date-badge .month,
    .event-date-badge .day,
    .event-date-badge .year {
      font-size: 1rem;
      margin: 0;
    }
  }
  
  @media (min-width: 768px) {
    .events-list {
      grid-template-columns: 1fr;
    }
  }

  /* Inline Event Sponsor Styles */
  .event-sponsors-inline {
    display: flex;
    align-items: center;
    gap: 1rem;
    margin-top: 0.75rem;
    margin-bottom: 1.5rem;
    padding: 0.75rem 0;
  }

  .sponsor-label {
    color: #6b7280;
    font-size: 0.85rem;
    font-weight: 500;
    white-space: nowrap;
  }

  .sponsors-inline-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 1.25rem;
    align-items: center;
  }

  .sponsor-inline-link {
    display: inline-block;
    transition: opacity 0.3s ease, transform 0.3s ease;
  }

  .sponsor-inline-link:hover {
    opacity: 0.7;
    transform: scale(1.05);
  }

  .sponsor-inline-logo {
    height: 32px;
    width: auto;
    max-width: 120px;
    object-fit: contain;
  }

  @media (max-width: 640px) {
    .event-sponsors-inline {
      flex-direction: column;
      align-items: flex-start;
      gap: 0.75rem;
    }

    .sponsor-inline-logo {
      height: 28px;
      max-width: 100px;
    }
  }

  /* Past Events Styles */
  .past-events-list {
    display: grid;
    grid-template-columns: 1fr;
    gap: 1.5rem;
    margin: 2rem 0;
  }

  .past-event-card {
    padding: 1.5rem;
    background-color: #f9fafb;
    border-radius: 8px;
    border: 1px solid #e5e7eb;
  }

  .past-event-header {
    display: flex;
    justify-content: space-between;
    align-items: baseline;
    margin-bottom: 0.5rem;
    flex-wrap: wrap;
    gap: 0.5rem;
  }

  .past-event-header h3 {
    margin: 0;
    color: #3C2FB3;
    font-size: 1.25rem;
  }

  .past-event-date {
    color: #6b7280;
    font-size: 0.9rem;
    font-weight: 500;
  }

  .past-event-subtitle {
    color: #4b5563;
    font-style: italic;
    margin-bottom: 0.75rem;
  }

  .past-event-location {
    color: #6b7280;
    font-size: 0.9rem;
    margin-top: 0.5rem;
  }

  /* Past Event Speakers */
  .past-event-speakers {
    margin-top: 1rem;
    padding-top: 1rem;
    border-top: 1px solid #e5e7eb;
  }

  .past-event-label {
    display: block;
    font-size: 0.8rem;
    font-weight: 600;
    color: #6b7280;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    margin-bottom: 0.75rem;
  }

  .past-speakers-list {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
  }

  .past-speaker {
    display: flex;
    align-items: center;
    gap: 0.75rem;
  }

  .past-speaker-photo {
    width: 48px;
    height: 48px;
    border-radius: 50%;
    object-fit: cover;
    border: 2px solid #3C2FB3;
  }

  .past-speaker-info {
    display: flex;
    flex-direction: column;
  }

  .past-speaker-name {
    font-weight: 600;
    color: #1f2937;
    font-size: 0.95rem;
  }

  .past-speaker-role {
    color: #6b7280;
    font-size: 0.85rem;
  }

  /* Past Event Sponsors */
  .past-event-sponsors {
    margin-top: 1rem;
    padding-top: 1rem;
    border-top: 1px solid #e5e7eb;
  }

  .past-sponsors-list {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    align-items: center;
  }

  .past-sponsor-link {
    display: inline-block;
    transition: opacity 0.3s ease;
  }

  .past-sponsor-link:hover {
    opacity: 0.7;
  }

  .past-sponsor-logo {
    height: 28px;
    width: auto;
    max-width: 100px;
    object-fit: contain;
  }

  @media (max-width: 640px) {
    .past-event-header {
      flex-direction: column;
      align-items: flex-start;
    }

    .past-speaker-photo {
      width: 40px;
      height: 40px;
    }
  }

  /* Coming Soon Card Styles */
  .coming-soon-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 3rem 2rem;
    border: 2px dashed #d1d5db;
    border-radius: 12px;
    background: linear-gradient(135deg, #f8f6ff 0%, #f3f4f6 100%);
  }

  .coming-soon-icon {
    color: #3C2FB3;
    margin-bottom: 1.5rem;
    opacity: 0.8;
  }

  .coming-soon-card h3 {
    color: #3C2FB3;
    margin-bottom: 0.75rem;
    font-size: 1.5rem;
  }

  .coming-soon-card p {
    color: #4b5563;
    max-width: 400px;
    margin-bottom: 1.5rem;
    line-height: 1.6;
  }

  @media (max-width: 640px) {
    .coming-soon-card {
      padding: 2rem 1.5rem;
    }

    .coming-soon-card h3 {
      font-size: 1.25rem;
    }
  }
</style>