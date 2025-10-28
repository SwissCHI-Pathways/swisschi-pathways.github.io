---
layout: default
title: Events
---

<div class="container">
  <div class="page-header">
    <h1>Upcoming Events</h1>
    <p class="lead">Join us for workshops, lectures, and networking events to enhance your HCI knowledge and connect with peers.</p>
  </div>
  
  <div class="events-list">
    <div class="event-card">
      <div class="event-date-badge">
        <span class="month">NOV</span>
        <span class="day">28</span>
        <span class="year">2025</span>
      </div>
      <div class="event-content">
        <h3>SwissCHI Pathways Cozy Research</h3>
        <h5><span class="text-muted">Exploring a softer kind of inquiry</span></h5>
        <p>A meet-up for BSc, MSc, and PhD students to share skills, spark strange ideas, and imagine research that warms, comforts, and connects. And to enjoy together the glowing lights and the cinnamon air of the Bern winter market.</p>

        <div class="event-schedule">
          <h4>Schedule</h4>
          <div class="schedule-item">
            <strong>11:00–11:15 | Arrival & Welcome</strong>
            <p>Check-in & Coffee: Tea and coffees, name tags</p>
          </div>
          <div class="schedule-item">
            <strong>11:15–12:15 | Guest Talk</strong>
            <p>Doga Dogan, PhD - Research Scientist @ Adobe Basel</p>
            <p><em>Q&A Session (15–20 min)</em></p>
          </div>
          <div class="schedule-item">
            <strong>12:15–13:45 | Skill-Sharing & Networking Lunch</strong>
            <p><em>Activity Setup:</em> Each participant fills out a card with:</p>
            <ul>
              <li>What I do (research area)</li>
              <li>What I am good at (skills)</li>
              <li>What I need (collaboration, mentorship, tools)</li>
            </ul>
            <p>Cards are color-coded or grouped by themes. Lunch Bag provided.</p>
          </div>
          <div class="schedule-item">
            <strong>13:45–15:45 | Cozy Research Challenge</strong>
            <p><em>Group Formation:</em> Groups of 3-4 people.</p>
            <p><em>Challenge Brief:</em> Each group receives a set of "cozy prompt cards" (e.g., tech that hugs back, HCI for tea drinkers…).</p>
            <p><em>Task:</em> Come up with a wildly cozy HCI research idea, sketch it out, and prepare a poster.</p>
            <p><em>Mini Presentations (15:15–15:45):</em> Who wants can share their idea with the room.</p>
          </div>
          <div class="schedule-item">
            <strong>16:00–... | Winter Market Visit</strong>
            <p>Walk to Bern Christmas Markets: Group stroll</p>
          </div>
        </div>

        <div class="event-details">
          <div class="event-detail">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
              <path d="M8 16s6-5.686 6-10A6 6 0 0 0 2 6c0 4.314 6 10 6 10zm0-7a3 3 0 1 1 0-6 3 3 0 0 1 0 6z"/>
            </svg>
            <span>Bern, BFH Marzili Campus</span>
          </div>
          <div class="event-detail">
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
              <path d="M8 3.5a.5.5 0 0 0-1 0V9a.5.5 0 0 0 .252.434l3.5 2a.5.5 0 0 0 .496-.868L8 8.71V3.5z"/>
              <path d="M8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16zm7-8A7 7 0 1 1 1 8a7 7 0 0 1 14 0z"/>
            </svg>
            <span>11:00 - 18:00</span>
          </div>
        </div>
        <a href="https://forms.gle/dAUbAaQ1BqLZHrjcA" target="_blank" class="btn btn-primary">Register</a>
      </div>
    </div>
  </div>
  
  <h2>Past Events</h2>
  
  <p>No past events yet. Stay tuned for our upcoming launch!</p>
  
  <div class="subscribe-events mt-3">
    <h3>Stay Updated</h3>
    <p>Don't miss out on our upcoming events. Subscribe to our newsletter to receive event announcements directly in your inbox.</p>
    <form class="subscribe-form">
      <input type="email" placeholder="Your email address" required>
      <button type="submit" class="btn btn-secondary">Subscribe</button>
    </form>
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
  }
  
  .subscribe-form {
    display: flex;
    gap: 1rem;
    margin-top: 1rem;
  }
  
  .subscribe-form input {
    flex: 1;
    padding: 0.75rem 1rem;
    border: 1px solid #e5e7eb;
    border-radius: 30px;
    font-size: 1rem;
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
    
    .subscribe-form {
      flex-direction: column;
    }
  }
  
  @media (min-width: 768px) {
    .events-list {
      grid-template-columns: 1fr;
    }
  }
</style>