<template>
  <div class="mailform-container w-full max-w-md p-2 mb-8 shadow">
    <div id="mc_embed_shell">
      <div id="mc_embed_signup">
        <form @submit.prevent="submitForm" id="mc-embedded-subscribe-form" class="validate" novalidate>
          <div id="mc_embed_signup_scroll">

          <div class="mc-field-group">
            <label for="mce-EMAIL">Email Address *</label>
            <input type="email" name="EMAIL" id="mce-EMAIL" v-model="email" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-FNAME">First Name *</label>
            <input type="text" name="FNAME" id="mce-FNAME" v-model="fname" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-LNAME">Last Name *</label>
            <input type="text" name="LNAME" id="mce-LNAME" v-model="lname" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-PHONE">Phone Number</label>
            <input type="text" name="PHONE" id="mce-PHONE" v-model="phone" />
          </div>

          <div class="mc-field-group">
            <label for="mce-COMPANY">Company *</label>
            <input type="text" name="COMPANY" id="mce-COMPANY" v-model="company" required />
          </div>

          <div class="mc-field-group">
            <label for="mce-MMERGE8">Type of interest *</label>
            <select name="MMERGE8" id="mce-MMERGE8" v-model="type" required>
              <option value="">Select</option>
              <option value="Client">Client</option>
              <option value="Broker">Broker</option>
            </select>
          </div>

            <div style="position:absolute; left:-5000px;" aria-hidden="true">
              <input type="text" tabindex="-1" value="">
            </div>

            <div class="clear">
              <input type="submit" class="button" :value="loading ? 'Sending...' : 'Subscribe'" :disabled="loading" />
            </div>

            <p class="mt-3 text-center font-semibold h-[.5rem]" :class="messageStyle">
              {{ message }}
            </p>

          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const email = ref('')
const fname = ref('')
const lname = ref('')
const phone = ref('')
const company = ref('')
const type = ref('')
const message = ref('')
const messageStyle = ref('')
const loading = ref(false)

//const base = `https://gmail.us1.list-manage.com/subscribe/post-json?u=5f24cdd4adbd1891f5cf5dfb2&id=bea7d670d0&c=mcCallback`
const base = 'https://mered.us14.list-manage.com/subscribe/post-json?u=25d9f5ec8a822907272418248&id=d82a44652e&c=mcCallback'

function submitForm() {
  loading.value = true
  message.value = ''
  messageStyle.value = ''

  const url =
    base +
    `&EMAIL=${encodeURIComponent(email.value)}` +
    `&FNAME=${encodeURIComponent(fname.value)}` +
    `&LNAME=${encodeURIComponent(lname.value)}` +
    `&PHONE=${encodeURIComponent(phone.value)}` +
    `&COMPANY=${encodeURIComponent(company.value)}` +
    `&MMERGE8=${encodeURIComponent(type.value)}`

  const script = document.createElement('script')
  script.src = url
  document.body.appendChild(script)

  window.mcCallback = data => {
    loading.value = false
    // console.log('data ', data)
    if (data.result === 'success') {
      message.value = 'Thank you — your request has been received.'
      messageStyle.value = 'text-white'
    } else {
      message.value = 'Error sending. Please check the fields and try again.'
      messageStyle.value = 'text-red'
    }
    script.remove();
    setTimeout(() => {
      email.value = '';
      fname.value = '';
      lname.value = '';
      phone.value = '';
      company.value = '';
      type.value = '';
      message.value = '';
      messageStyle.value = '';
    }, 5000);
  }
}

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
