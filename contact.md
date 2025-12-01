---
layout: default
title: Contact Us
description: "Get in touch with SwissCHI Pathways. We'd love to hear from students, researchers, and sponsors."
---

<div class="container">
  <h1>Contact Us</h1>
  
  <p>Have questions about SwissCHI Pathways or want to get in touch? We'd love to hear from you!</p>
  
  <div class="contact-info">
    <div class="contact-method">
      <h3>Email</h3>
      <p><a href="mailto:swiss.pathways@gmail.com">swiss.pathways@gmail.com</a></p>
    </div>
    
    <div class="contact-method">
      <h3>Social Media</h3>
      <ul class="social-links">
        <li><a href="https://www.linkedin.com/company/swisschi-pathways/" target="_blank">LinkedIn</a></li>
      </ul>
    </div>
  </div>
  
  <h2>Send Us a Message</h2>
  
  <div class="form-container">
    <div class="google-form-wrapper">
      <iframe id="contact-form" src="https://docs.google.com/forms/d/e/1FAIpQLSeiUVy4RcPbxBUmvuhuQPrkMgNSr21mwisPnMpQcfF81wU0cg/viewform?embedded=true" title="SwissCHI Pathways contact form" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
    </div>

    <div class="form-alternative">
      <p>Having trouble with the form? <a href="https://docs.google.com/forms/d/e/1FAIpQLSeiUVy4RcPbxBUmvuhuQPrkMgNSr21mwisPnMpQcfF81wU0cg/viewform" target="_blank" class="btn btn-outline">Open in a new tab</a></p>
    </div>
  </div>
</div>

<style>
  .contact-info {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin: 2rem 0;
  }
  
  .contact-method {
    background-color: #f3f4f6;
    padding: 1.5rem;
    border-radius: 8px;
  }
  
  .social-links {
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  .social-links li {
    margin-bottom: 0.5rem;
  }
  
  .form-container {
    margin: 2rem 0;
    max-width: 700px;
  }
  
  .google-form-wrapper {
    position: relative;
    overflow: hidden;
    padding-top: 90%; /* Aspect ratio for mobile */
    border-radius: 12px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
    border: 1px solid #e5e7eb;
    background-color: #f9fafb;
  }
  
  @media (min-width: 768px) {
    .google-form-wrapper {
      padding-top: 120%; /* Adjusted aspect ratio for desktop */
    }
  }
  
  #contact-form {
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
    
    var iframe = document.getElementById('contact-form');
    if (iframe) {
      var newHeight = Math.max(message.frameHeight + 30, 450) + 'px';
      document.querySelector('.google-form-wrapper').style.height = newHeight;
      document.querySelector('.google-form-wrapper').style.paddingTop = '0';
    }
  });
</script>