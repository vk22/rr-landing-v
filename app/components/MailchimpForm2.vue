<template>
  <div class="mailform-container w-full max-w-md p-2 mb-8 shadow">
  <div id="mc_embed_shell" class="mailchimp-form">
    <div id="mc_embed_signup">
      <form
        action="https://gmail.us1.list-manage.com/subscribe/post?u=5f24cdd4adbd1891f5cf5dfb2&amp;id=bea7d670d0&amp;f_id=00492fe5f0"
        method="post"
        id="mc-embedded-subscribe-form"
        name="mc-embedded-subscribe-form"
        class="validate"
        target="_blank"
        novalidate
      >
        <div id="mc_embed_signup_scroll">
          <h2>Subscribe</h2>
          <div class="indicates-required">
            <span class="asterisk">*</span> indicates required
          </div>

          <div class="mc-field-group">
            <label for="mce-EMAIL">
              Email Address <span class="asterisk">*</span>
            </label>
            <input
              type="email"
              name="EMAIL"
              class="required email"
              id="mce-EMAIL"
              required
            />
          </div>

          <div class="mc-field-group">
            <label for="mce-FNAME">First Name </label>
            <input type="text" name="FNAME" id="mce-FNAME" />
          </div>

          <div class="mc-field-group">
            <label for="mce-LNAME">Last Name </label>
            <input type="text" name="LNAME" id="mce-LNAME" />
          </div>

          <div id="mce-responses" class="clear foot">
            <div class="response" id="mce-error-response" style="display:none"></div>
            <div class="response" id="mce-success-response" style="display:none"></div>
          </div>

          <div aria-hidden="true" style="position:absolute; left:-5000px;">
            <input
              type="text"
              name="b_5f24cdd4adbd1891f5cf5dfb2_bea7d670d0"
              tabindex="-1"
              value=""
            />
          </div>

          <div class="optionalParent">
            <div class="clear foot">
              <input
                type="submit"
                name="subscribe"
                id="mc-embedded-subscribe"
                class="button"
                value="Subscribe"
              />
              <p style="margin: 0 auto;">
                <a
                  href="http://eepurl.com/jqAm6w"
                  title="Mailchimp - email marketing made easy and fun"
                >
                  <img
                    class="refferal_badge"
                    src="https://digitalasset.intuit.com/render/content/dam/intuit/mc-fe/en_us/images/intuit-mc-rewards-text-dark.svg"
                    alt="Intuit Mailchimp"
                    width="220"
                    height="40"
                  />
                </a>
              </p>
            </div>
          </div>
        </div>
      </form>
    </div>
  </div>
  </div>
</template>

<script setup>
import { onMounted } from "vue";

onMounted(() => {
  // Подключаем Mailchimp CSS
  const link = document.createElement("link");
  link.rel = "stylesheet";
  link.type = "text/css";
  link.href = "//cdn-images.mailchimp.com/embedcode/classic-061523.css";
  document.head.appendChild(link);

  // Подключаем Mailchimp JS (валидация и логика)
  const script = document.createElement("script");
  script.src = "//s3.amazonaws.com/downloads.mailchimp.com/js/mc-validate.js";
  script.async = true;
  document.body.appendChild(script);
});
</script>

<style scoped>
.mailform-container {
  width: 100%;
  max-width: 600px;
  background:#00000028;
}

.mailform-container label {
  color: #fff;
}

#mc_embed_signup {
  background: transparent;
  font: 14px Helvetica, Arial, sans-serif;
  width: 100%;
  max-width: 600px;
  margin: 0 auto;
}

#mc_embed_signup .mc-field-group {
    width: 100%!important;
}

#mc_embed_signup .mc-field-group input {
    background: #fff;
    border-radius: 0!important;
}

#mc_embed_signup .button {
    background-color: #0a4b5c!important;
    height: 46px!important;
    width: 100%!important;
    text-transform: uppercase;
    letter-spacing: 1px;
    border-radius: 0!important;
}

#mc_embed_signup select {
    background: #fff;
    border: 1px solid #ABB0B2;
    border-radius: 0!important;
    padding: 5px;
    width: 100%!important;
    padding: 10px 0!important;
    margin-bottom: 10px!important;
}
</style>
