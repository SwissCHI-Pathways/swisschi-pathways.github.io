---
layout: default
title: Events
---

<div class="container">
  <h1>Upcoming Events</h1>
  
  <div class="events-list">
    <div class="event-card">
      <div class="event-date">September 15, 2025</div>
      <h3>SwissCHI Pathways Launch Event</h3>
      <p>Join us for the official launch of the SwissCHI Pathways student chapter! Connect with fellow HCI students, learn about our planned activities, and enjoy refreshments.</p>
      <p><strong>Location:</strong> ETH Zurich, CAB Building</p>
      <p><strong>Time:</strong> 18:00 - 20:00</p>
      <a href="#" class="btn btn-primary">Register</a>
    </div>
    
    <div class="event-card">
      <div class="event-date">October 5, 2025</div>
      <h3>Workshop: Introduction to User Research Methods</h3>
      <p>A hands-on workshop covering fundamental user research methods for HCI projects. Learn how to plan, conduct, and analyze user research to inform your designs.</p>
      <p><strong>Location:</strong> University of Zurich, Binzmühlestrasse 14</p>
      <p><strong>Time:</strong> 14:00 - 17:00</p>
      <a href="#" class="btn btn-primary">Register</a>
    </div>
    
    <div class="event-card">
      <div class="event-date">November 12, 2025</div>
      <h3>Guest Lecture: The Future of Human-AI Interaction</h3>
      <p>Dr. Marta Rodriguez from EPFL will discuss emerging trends and challenges in Human-AI Interaction, followed by a Q&A session.</p>
      <p><strong>Location:</strong> Online via Zoom</p>
      <p><strong>Time:</strong> 19:00 - 20:30</p>
      <a href="#" class="btn btn-primary">Register</a>
    </div>
  </div>
  
  <h2>Past Events</h2>
  
  <p>No past events yet. Stay tuned for our upcoming launch!</p>
</div>

<style>
  .events-list {
    display: grid;
    grid-template-columns: 1fr;
    gap: 2rem;
    margin: 2rem 0;
  }
  
  .event-card {
    border: 1px solid #e5e7eb;
    border-radius: 8px;
    padding: 1.5rem;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  }
  
  .event-date {
    color: #2563eb;
    font-weight: bold;
    margin-bottom: 0.5rem;
  }
  
  @media (min-width: 768px) {
    .events-list {
      grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    }
  }
</style>