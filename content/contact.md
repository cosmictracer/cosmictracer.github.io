---
title: "Contact"
---

## Get in Touch

We're happy to hear from you!  
Questions, collaboration ideas, suggestions — send us a message anytime.

---

## Contact Form

<form action="https://formspree.io/f/xpwnvejr" method="POST" id="contact-form">

  <label for="name">Name</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email</label>
  <input type="email" id="email" name="_replyto" required>

  <label for="message">Message</label>
  <textarea id="message" name="message" rows="6" required></textarea>

  <div class="g-recaptcha" data-sitekey="6Ld9aBYsAAAAAIXw7d8DK0qcKRD0ICGUNy_BSnhp" data-callback="onCaptchaSuccess"></div>
  <input type="hidden" name="_captcha" id="captcha-response" required>

  <button type="submit" class="btn-submit">Send Message</button>

</form>

<script src="https://www.google.com/recaptcha/api.js" async defer></script>
<script>
  function onCaptchaSuccess(token) {
    document.getElementById('captcha-response').value = token;
  }
  
  document.getElementById('contact-form').addEventListener('submit', function(e) {
    const captchaValue = document.getElementById('captcha-response').value;
    if (!captchaValue) {
      e.preventDefault();
      return false;
    }
  });
</script>

---

## Alternatively, contact us at:

📧 **editor@cosmictracer.com**  
🌐 https://www.cosmictracer.com

