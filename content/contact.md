---
title: "Contact"
---

## Get in Touch

We're happy to hear from you!  
Questions, collaboration ideas, suggestions — send us a message anytime.

---

## Contact Form

<form id="contactForm" action="https://formspree.io/f/xpwnvejr" method="POST">

  <label for="name">Name</label>
  <input type="text" id="name" name="name" required>

  <label for="email">Email</label>
  <input type="email" id="email" name="email" required>

  <label for="message">Message</label>
  <textarea id="message" name="message" rows="6" required></textarea>

  <!-- Hidden field required by Formspree for reCAPTCHA v3 -->
  <input type="hidden" name="g-recaptcha-response" id="g-recaptcha-response">

  <button type="submit" id="submitBtn">Send Message</button>

</form>

<!-- Load reCAPTCHA v3 -->
<script src="https://www.google.com/recaptcha/api.js?render=6Ld9aBYsAAAAAIXw7d8DK0qcKRD0ICGUNy_BSnhp"></script>

<script>
document.getElementById("contactForm").addEventListener("submit", function(e) {
    e.preventDefault();

    grecaptcha.ready(function() {
        grecaptcha.execute("6Ld9aBYsAAAAAIXw7d8DK0qcKRD0ICGUNy_BSnhp", {action: "submit"})
        .then(function(token) {
            document.getElementById("g-recaptcha-response").value = token;
            e.target.submit();
        });
    });
});
</script>



---

## Alternatively, contact us at:

📧 **editor@cosmictracer.com**  
🌐 https://www.cosmictracer.com

