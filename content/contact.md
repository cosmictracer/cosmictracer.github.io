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

  <!-- hidden token field -->
  <input type="hidden" name="g-recaptcha-response" id="recaptcha-token">

  <button type="submit" class="btn-submit">Send Message</button>
</form>

<script src="https://www.google.com/recaptcha/api.js?render=6Ld9aBYsAAAAAIXw7d8DK0qcKRD0ICGUNy_BSnhp"></script>
<script>
  const siteKey = "6Ld9aBYsAAAAAIXw7d8DK0qcKRD0ICGUNy_BSnhp";

  grecaptcha.ready(function () {
    grecaptcha.execute(siteKey, { action: "submit" }).then(function (token) {
      document.getElementById("recaptcha-token").value = token;
    });
  });

  // regenerate token every time user tries to submit
  document.getElementById("contact-form").addEventListener("submit", function (e) {
    if (!document.getElementById("recaptcha-token").value) {
      e.preventDefault();
      grecaptcha.execute(siteKey, { action: "submit" }).then(function (token) {
        document.getElementById("recaptcha-token").value = token;
        document.getElementById("contact-form").submit();
      });
    }
  });
</script>


---

## Alternatively, contact us at:

📧 **editor@cosmictracer.com**  
🌐 https://www.cosmictracer.com

