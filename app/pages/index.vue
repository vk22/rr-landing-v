<template>
  <div class="landing-index transition-opacity duration-1000"  :class="{ 'opacity-100': imageLoaded, 'opacity-0': !imageLoaded }"
  
  >
    <section
      id="top"
      class="mx-auto max-w-5xl flex flex-col items-center text-center py-20 px-10"
    >
      <div class="logo mb-10 md:mb-16 transition-all duration-1000 delay-100"
      :class="{
        'opacity-100 translate-y-0': contentVisible,
        'opacity-0 translate-y-1': !contentVisible
      }">
        <img src="../assets/img/logo.svg" class="w-[200px] md:w-[250px]" alt="" />
      </div>

      <div class="text-1 transition-all duration-1000 delay-500"
      :class="{
        'opacity-100 translate-y-0': contentVisible,
        'opacity-0 translate-y-1': !contentVisible
      }">
        <h1 class="text-white mb-6 md:mb-6 md:mb-16 text-[2rem] md:text-[4rem] max-w-[900px]">
          Riviera Residences — <span class="text-accent color1">a new icon 
       
          of waterfront living </span>
          <br>
          <span class="text-accent light-blue">on Al Reem Island, Abu Dhabi</span> 
        </h1>
      </div>

      <div class="text-2 transition-all duration-1000 delay-500"
       :class="{
        'opacity-100 translate-y-0': contentVisible,
        'opacity-0 translate-y-1': !contentVisible
      }">
        <p class="text-white mb-4 md:mb-8 text-[.9rem] md:text-[1.15rem] max-w-lg">
          Architecture by Herzog & de Meuron — Pritzker Prize laureates and authors of some of the most iconic architecture of the 21st century.
        </p>
      </div>

      <div class="text-2 transition-all duration-1000 delay-500"
       :class="{
        'opacity-100 translate-y-0': contentVisible,
        'opacity-0 translate-y-1': !contentVisible
      }">
        <p class="text-white mb-6 md:mb-12 text-[.9rem] md:text-[1.15rem] max-w-lg">
          Blending Mediterranean serenity with the spirit of the Emirates, Riviera Residences offers the comfort of a private resort — with refined design, waterfront promenade, and world-class amenities.
        </p>
      </div>

      <div class="text-2 transition-all duration-1000 delay-500"
       :class="{
        'opacity-100 translate-y-0': contentVisible,
        'opacity-0 translate-y-1': !contentVisible
      }">
        <p class="text-white text-lg md:text-xl mb-10 md:mb-12 max-w-lg">
          <span class="font-sans text-[1.5rem] md:text-[2rem]">Sales start in</span> <span class="font-sans-italic text-[1.5rem] md:text-[2rem]">November</span>
          <br>
          <span class="font-grotesk uppercase tracking-[.12em] text-[1rem] md:text-[1.35rem] leading-[2rem]">Express your interest</span>
        </p>
      </div>
<!-- 
      <div class="text-2">
        <p class="text-white text-lg md:text-xl mb-6 md:mb-8 max-w-lg">Register your interest today </p>
      </div> -->
      
      <MailchimpForm class="transition-all duration-1000 delay-700"
       :class="{
        'opacity-100 translate-y-0': contentVisible,
        'opacity-0 translate-y-1': !contentVisible
      }"></MailchimpForm>
    
      <div class="text-2">
        <p class="text-white text-m max-w-xl mb-4 md:mb-8">Attendance is by invitation only — spaces are limited, and QR-coded invites will be sent one week before the event. </p>
      </div>

    <div class="logo mb-1">
        <img class="max-w-30" src="../assets/img/mered.svg" alt="" />
      </div>

    </section>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
const imageLoaded = ref(false);
const backgroundUrl = '/img/background.jpg' ;
const contentVisible = ref(false);

onMounted(() => {
  const img = new Image();
  img.src = backgroundUrl;
  img.onload = () => {
    imageLoaded.value = true;
    setTimeout(() => (contentVisible.value = true), 300)
  }
})
</script>

<style scoped>
.landing-index {
  height: 100vh;
  position: relative;
  background-image: linear-gradient(rgba(0, 0, 0, 0.827),rgba(0, 0, 0, 0.5)), url("/img/background.jpg");
  background-position: center center;
  background-size: cover;
  overflow: scroll;
}


</style>