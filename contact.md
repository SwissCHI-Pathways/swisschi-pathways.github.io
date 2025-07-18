---
layout: default
title: Contact Us
---

<div class="container">
  <h1>Contact Us</h1>
  
  <p>Have questions about SwissCHI Pathways or want to get in touch? We'd love to hear from you!</p>
  
  <div class="contact-info">
    <div class="contact-method">
      <h3>Email</h3>
      <p><a href="mailto:info@swisschi-pathways.ch">info@swisschi-pathways.ch</a></p>
    </div>
    
    <div class="contact-method">
      <h3>Social Media</h3>
      <ul class="social-links">
        <li><a href="#" target="_blank">Twitter</a></li>
        <li><a href="#" target="_blank">LinkedIn</a></li>
        <li><a href="#" target="_blank">Instagram</a></li>
      </ul>
    </div>
  </div>
  
  <h2>Send Us a Message</h2>
  
  <div class="form-container">
    <form id="contact-form" action="#" method="POST">
      <div class="form-group">
        <label for="name">Your Name *</label>
        <input type="text" id="name" name="name" required>
      </div>
      
      <div class="form-group">
        <label for="email">Email Address *</label>
        <input type="email" id="email" name="email" required>
      </div>
      
      <div class="form-group">
        <label for="subject">Subject *</label>
        <input type="text" id="subject" name="subject" required>
      </div>
      
      <div class="form-group">
        <label for="message">Message *</label>
        <textarea id="message" name="message" rows="5" required></textarea>
      </div>
      
      <div class="form-group">
        <button type="submit" class="btn btn-primary">Send Message</button>
      </div>
    </form>
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
    max-width: 600px;
  }
  
  .form-group {
    margin-bottom: 1.5rem;
  }
  
  label {
    display: block;
    margin-bottom: 0.5rem;
    font-weight: 500;
  }
  
  input[type="text"],
  input[type="email"],
  textarea {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #e5e7eb;
    border-radius: 4px;
    font-family: inherit;
    font-size: 1rem;
  }
  
  textarea {
    resize: vertical;
  }
</style>