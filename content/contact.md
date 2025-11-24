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

  <!-- hidden token field for reCAPTCHA v3 -->
  <input type="hidden" name="g-recaptcha-response" id="recaptcha-token">

  <button type="submit" class="btn-submit">Send Message</button>
</form>

<script src="https://www.google.com/recaptcha/api.js?render=6Ld9aBYsAAAAAIXw7d8DK0qcKRD0ICGUNy_BSnhp"></script>
<script>
  const siteKey = "6Ld9aBYsAAAAAIXw7d8DK0qcKRD0ICGUNy_BSnhp";
  const form = document.getElementById("contact-form");
  const tokenField = document.getElementById("recaptcha-token");
  let isSubmitting = false;

  // Função para gerar token do reCAPTCHA
  function generateToken() {
    return grecaptcha.execute(siteKey, { action: "submit" });
  }

  // Inicializar reCAPTCHA e gerar token inicial quando a página carregar
  grecaptcha.ready(function () {
    generateToken().then(function (token) {
      if (token) {
        tokenField.value = token;
      }
    }).catch(function(error) {
      console.error("Erro ao gerar token inicial:", error);
    });
  });

  // Handler de submit do formulário
  function handleSubmit(e) {
    // Prevenir múltiplos submits
    if (isSubmitting) {
      e.preventDefault();
      return false;
    }

    // Prevenir submit imediato para gerar token fresco
    e.preventDefault();
    isSubmitting = true;

    // Desabilitar botão de submit para evitar múltiplos cliques
    const submitButton = form.querySelector('button[type="submit"]');
    const originalButtonText = submitButton.textContent;
    submitButton.disabled = true;
    submitButton.textContent = "Enviando...";

    // Gerar novo token antes de enviar (tokens expiram após alguns minutos)
    generateToken()
      .then(function (token) {
        if (!token) {
          throw new Error("Token não foi gerado");
        }
        
        // Atualizar o campo com o token
        tokenField.value = token;
        
        // Verificar se o token foi realmente definido
        if (!tokenField.value || tokenField.value.length === 0) {
          throw new Error("Token não foi definido no campo");
        }

        // Log para debug (remover em produção se necessário)
        console.log("Token reCAPTCHA gerado:", tokenField.value.substring(0, 20) + "...");

        // Usar submit nativo do formulário para garantir compatibilidade com Formspree
        // Remover o event listener temporariamente para evitar loop infinito
        form.removeEventListener("submit", handleSubmit);
        
        // Pequeno delay para garantir que o token seja processado
        setTimeout(function() {
          // Usar requestSubmit() se disponível (mais moderno) ou submit() como fallback
          if (typeof form.requestSubmit === 'function') {
            form.requestSubmit();
          } else {
            form.submit();
          }
        }, 100);
      })
      .catch(function(error) {
        console.error("Erro ao gerar token reCAPTCHA:", error);
        alert("Erro ao validar reCAPTCHA. Recarregue a página e tente novamente.");
        isSubmitting = false;
        submitButton.disabled = false;
        submitButton.textContent = originalButtonText;
      });
  }

  // Adicionar event listener
  form.addEventListener("submit", handleSubmit);
</script>


---

## Alternatively, contact us at:

📧 **editor@cosmictracer.com**  
🌐 https://www.cosmictracer.com

