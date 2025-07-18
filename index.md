---
layout: home
title: SwissCHI Pathways
---

<div class="home-logo-container">
  <img src="{{ '/assets/images/PatwaysLogo_Symbol_Purple.svg' | relative_url }}" alt="Pathways Symbol" class="home-logo">
</div>

SwissCHI Pathways is the student chapter of the Swiss Computer-Human Interaction Association, connecting students and young professionals in the field of Human-Computer Interaction across Switzerland.

<div class="cta-buttons">
  <a href="{{ '/join' | relative_url }}" class="btn btn-primary">Join Us</a>
  <a href="{{ '/events' | relative_url }}" class="btn btn-secondary">Upcoming Events</a>
  <a href="{{ '/about' | relative_url }}" class="btn btn-outline">Learn More</a>
</div>

<style>
.home-logo-container {
  margin-bottom: 2rem;
}

.home-logo {
  height: 100px;
  width: auto;
  margin: 0 auto;
  display: block;
  animation: pulse 4s infinite;
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
  100% {
    transform: scale(1);
  }
}
</style>