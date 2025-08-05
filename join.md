---
layout: default
title: Join SwissCHI Pathways
---

<div class="container">
  <h1>Join SwissCHI Pathways</h1>
  
  <p>We're excited that you're interested in joining the SwissCHI Pathways community! As a member, you'll have access to networking opportunities, events, resources, and a community of like-minded students and researchers in the field of Human-Computer Interaction.</p>
  
  <h2>Membership Benefits</h2>
  
  <ul>
    <li>Access to all SwissCHI Pathways events and workshops</li>
    <li>Networking opportunities with HCI students across Switzerland</li>
    <li>Opportunities to collaborate on research and projects</li>
    <li>Resources and learning materials for HCI topics</li>
    <li>Mentorship from experienced HCI professionals</li>
    <li>Discounted entry to SwissCHI events</li>
  </ul>
  
  <h2>Eligibility</h2>
  
  <p>Membership is open to all students enrolled in Swiss universities and educational institutions who are interested in Human-Computer Interaction, regardless of their field of study.</p>
  
  <h2>How to Join</h2>
  
  <p>Fill out the membership form below, and we'll get back to you with confirmation and next steps.</p>
  
  <div class="form-container">
    <div class="google-form-wrapper">
      <iframe id="google-form" src="https://docs.google.com/forms/d/e/1FAIpQLSekT5LS90RiTTOAxb_j2UWkH2AExUJYVlmh8DSiuE2HNKaZKg/viewform?embedded=true" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
    </div>
    
    <div class="form-alternative">
      <p>Having trouble with the form? <a href="https://docs.google.com/forms/d/e/1FAIpQLSekT5LS90RiTTOAxb_j2UWkH2AExUJYVlmh8DSiuE2HNKaZKg/viewform" target="_blank" class="btn btn-outline">Open in a new tab</a></p>
    </div>
  </div>
</div>

<style>
  .form-container {
    margin: 2rem 0;
    max-width: 700px;
  }
  
  .google-form-wrapper {
    position: relative;
    overflow: hidden;
    padding-top: 100%; /* Aspect ratio for mobile */
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    border: 1px solid #e5e7eb;
    background-color: #f9fafb;
  }
  
  @media (min-width: 768px) {
    .google-form-wrapper {
      padding-top: 150%; /* Taller aspect ratio for desktop */
    }
  }
  
  #google-form {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
  }
  
  .form-alternative {
    margin-top: 1.5rem;
    text-align: center;
    padding: 1rem;
    background-color: #f3f4f6;
    border-radius: 8px;
  }
  
  .form-alternative p {
    margin-bottom: 0;
  }
  
  .form-alternative .btn {
    margin-left: 0.5rem;
    padding: 0.25rem 0.75rem;
  }
</style>

<script>
  // Adjust iframe height based on content
  window.addEventListener('message', function(e) {
    var message = e.data;
    if (typeof message !== 'object' || !message.hasOwnProperty('frameHeight')) return;
    
    var iframe = document.getElementById('google-form');
    if (iframe) {
      var newHeight = Math.max(message.frameHeight + 30, 500) + 'px';
      document.querySelector('.google-form-wrapper').style.height = newHeight;
      document.querySelector('.google-form-wrapper').style.paddingTop = '0';
    }
  });
</script>