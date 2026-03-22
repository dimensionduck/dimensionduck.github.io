---
title: Contact
icon: fas fa-envelope
order: 7
---

Use the form below to send a message without showing my email address on the page.

<form id="contact-form" class="mt-4">
  <div class="mb-3">
    <label class="form-label" for="contact-name">Name</label>
    <input class="form-control" id="contact-name" name="name" type="text" placeholder="Your name" required>
  </div>

  <div class="mb-3">
    <label class="form-label" for="contact-email">Your Email</label>
    <input class="form-control" id="contact-email" name="email" type="email" placeholder="you@example.com" required>
  </div>

  <div class="mb-3">
    <label class="form-label" for="contact-subject">Subject</label>
    <input class="form-control" id="contact-subject" name="subject" type="text" placeholder="What is this about?" required>
  </div>

  <div class="mb-3">
    <label class="form-label" for="contact-message">Message</label>
    <textarea class="form-control" id="contact-message" name="message" rows="6" placeholder="Write your message here." required></textarea>
  </div>

  <input type="hidden" name="_captcha" value="false">
  <input type="hidden" name="_template" value="table">

  <button class="btn btn-primary" type="submit">Send Message</button>
  <p class="mt-3 mb-0 text-muted" id="contact-status"></p>
</form>

{% assign email_parts = site.social.email | split: '@' %}
<script>
  document.addEventListener('DOMContentLoaded', function() {
    const form = document.getElementById('contact-form');
    const status = document.getElementById('contact-status');
    const emailUser = {{ email_parts[0] | jsonify }};
    const emailDomain = {{ email_parts[1] | jsonify }};

    form.addEventListener('submit', async function(event) {
      event.preventDefault();

      if (!emailUser || !emailDomain) {
        status.textContent = 'Contact is not configured yet.';
        return;
      }

      const email = emailUser + '@' + emailDomain;
      const submitButton = form.querySelector('button[type="submit"]');
      const formData = new FormData(form);

      submitButton.disabled = true;
      status.textContent = 'Sending message...';

      try {
        const response = await fetch('https://formsubmit.co/ajax/' + encodeURIComponent(email), {
          method: 'POST',
          headers: {
            Accept: 'application/json'
          },
          body: formData
        });

        if (!response.ok) {
          throw new Error('Request failed');
        }

        status.textContent = 'Message sent successfully.';
        form.reset();
      } catch (error) {
        status.textContent = 'Message could not be sent right now. Please try again later.';
      } finally {
        submitButton.disabled = false;
      }
    });
  });
</script>
