<template>
  <div class="mailform-container w-full max-w-md p-2 mb-8 shadow">
  <div id="mc_embed_shell">
    <div id="mc_embed_signup">
      <form
        action="https://mered.us14.list-manage.com/subscribe/post?u=25d9f5ec8a822907272418248&amp;id=d82a44652e&amp;f_id=0016a2e1f0"
        method="post"
        id="mc-embedded-subscribe-form"
        name="mc-embedded-subscribe-form"
        class="validate"
        target="_blank"
        novalidate
      >
        <div id="mc_embed_signup_scroll">
          <!-- <h2>Subscribe</h2> -->

          <div class="mc-field-group">
            <label for="mce-EMAIL">Email Address *</label>
            <input type="email" name="EMAIL" id="mce-EMAIL" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-FNAME">First Name *</label>
            <input type="text" name="FNAME" id="mce-FNAME" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-LNAME">Last Name *</label>
            <input type="text" name="LNAME" id="mce-LNAME" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-PHONE">Phone Number</label>
            <input type="text" name="PHONE" id="mce-PHONE" />
          </div>

          <div class="mc-field-group">
            <label for="mce-COMPANY">Company *</label>
            <input type="text" name="COMPANY" id="mce-COMPANY" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-MMERGE8">Type of interest *</label>
            <select name="MMERGE8" id="mce-MMERGE8" required>
              <option value="">Select</option>
              <option value="Client">Client</option>
              <option value="Broker">Broker</option>
            </select>
          </div>

          

          <div style="position: absolute; left: -5000px;" aria-hidden="true">
            <input type="text" name="b_25d9f5ec8a822907272418248_d82a44652e" tabindex="-1" value="">
          </div>

          <div class="clear">
            <input type="submit" value="Subscribe" class="button" />
          </div>

          <div id="mce-responses" class="clear foot">
            <div class="response" id="mce-error-response" style="display:none"></div>
            <div class="response" id="mce-success-response" style="display:none"></div>
          </div>
        </div> 
      </form>
    </div>
  </div>
  </div>
</template>

<script setup>
onMounted(() => {
  const style = document.createElement("link")
  style.rel = "stylesheet"
  style.href = "//cdn-images.mailchimp.com/embedcode/classic-061523.css"
  document.head.appendChild(style)

  const script = document.createElement("script")
  script.src = "//s3.amazonaws.com/downloads.mailchimp.com/js/mc-validate.js"
  script.onload = () => {
    console.log("Mailchimp JS loaded")
  }
  document.body.appendChild(script)

  // const successEl = document.getElementById("mce-success-response");
  // if (successEl) {
  //   const observer = new MutationObserver(() => {
  //     if (successEl.style.display !== "none" && successEl.innerText.trim() !== "") {
  //       // Меняем текст
  //       successEl.innerHTML = "Thank you — your request has been received.";
  //     }
  //   });
  //   observer.observe(successEl, { childList: true, subtree: true });
  // }
})
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

#mc_embed_signup div#mce-responses {
    display: flex;
    float: left;
    top: -1.4em;
    padding: 0;
    overflow: hidden;
    width: 100%;
    margin: 0;
    clear: both;
}

#mc_embed_signup #mce-success-response {
    color: #fff;
    display: none;
    text-align: center;
    width: 100%;
}

</style>
