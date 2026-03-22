---
title: Contact
icon: fas fa-envelope
order: 7
---

Use the form below to draft a message without showing my email address on the page.

<form id="contact-form" class="mt-4">
  <div class="mb-3">
    <label class="form-label" for="contact-name">Name</label>
    <input class="form-control" id="contact-name" name="name" type="text" placeholder="Your name" required>
  </div>

  <div class="mb-3">
    <label class="form-label" for="contact-subject">Subject</label>
    <input class="form-control" id="contact-subject" name="subject" type="text" placeholder="What is this about?" required>
  </div>

  <div class="mb-3">
    <label class="form-label" for="contact-message">Message</label>
    <textarea class="form-control" id="contact-message" name="message" rows="6" placeholder="Write your message here." required></textarea>
  </div>

  <button class="btn btn-primary" type="submit">Open Email Draft</button>
  <p class="mt-3 mb-0 text-muted" id="contact-status"></p>
</form>

{% assign email_parts = site.social.email | split: '@' %}
<script>
  document.addEventListener('DOMContentLoaded', function() {
    const form = document.getElementById('contact-form');
    const status = document.getElementById('contact-status');
    const emailUser = {{ email_parts[0] | jsonify }};
    const emailDomain = {{ email_parts[1] | jsonify }};

    form.addEventListener('submit', function(event) {
      event.preventDefault();

      if (!emailUser || !emailDomain) {
        status.textContent = 'Contact is not configured yet.';
        return;
      }

      const name = document.getElementById('contact-name').value.trim();
      const subject = document.getElementById('contact-subject').value.trim();
      const message = document.getElementById('contact-message').value.trim();
      const email = emailUser + '@' + emailDomain;
      const body = 'Name: ' + name + '\n\n' + message;
      const mailto = 'mailto:' + encodeURIComponent(email) +
        '?subject=' + encodeURIComponent(subject) +
        '&body=' + encodeURIComponent(body);

      window.location.href = mailto;
      status.textContent = 'Your email app should open with a drafted message.';
    });
  });
</script>
