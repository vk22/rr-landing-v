<template>
  <div
    class="landing-index transition-opacity duration-1000"
    :class="{ 'opacity-100': imageLoaded, 'opacity-0': !imageLoaded }"
  >
    <div class="content-container">
      <section
        id="top"
        class="mx-auto max-w-5xl flex flex-col items-center text-center py-20 px-10"
      >
        <div
          class="logo mb-16 md:mb-24 transition-all duration-1000 delay-100"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        >
          <img
            src="../assets/img/logo.svg"
            class="w-[200px] md:w-[250px]"
            alt=""
          />
        </div>

        <div
          class="mb-6 md:mb-8 max-w-[900px] transition-all duration-1000 delay-500"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        >
          <h1 class="text-white text-[2rem] md:text-[4rem]">
            <div class="uppercase">
              a new icon of
            </div>
            <div class="uppercase">
              waterfront <span class="text-accent light-blue">living</span>
            </div>
          </h1>
        </div>

        <div
          class="mb-12 md:mb-16 max-w-lg transition-all duration-1000 delay-500"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        >
          <p
            class="text-white uppercase text-[.9rem] md:text-[1.25rem] tracking-[.1em]"
          >
            Al Reem Island,<br />
            Abu Dhabi
          </p>
        </div>

        <div
          class="mb-4 md:mb-8 max-w-lg transition-all duration-1000 delay-500"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        >
          <p class="text-white text-[.9rem] md:text-[1.1rem]">
            Architecture by Herzog & de Meuron — Pritzker Prize laureates and
            authors of some of the most iconic architecture of the 21st century.
          </p>
        </div>

        <div
          class="mb-8 md:mb-12 max-w-lg transition-all duration-1000 delay-500"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        >
          <p class="text-white text-[.9rem] md:text-[1.1rem]">
            Blending Mediterranean serenity with the spirit of the Emirates,
            Riviera Residences offers the comfort of a private resort — with
            refined design, waterfront promenade, and world-class amenities.
          </p>
        </div>

        <div
          class="mb-3 md:mb-4 max-w-lg transition-all duration-1000 delay-500"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        >
          <p class="text-white text-lg md:text-xl">
            <span class="font-sans text-[1.5rem] md:text-[2rem]"
              >Sales start in
            </span>
            <span
              class="font-sans-italic text-[1.5rem] md:text-[2rem] light-blue"
              >November</span
            >
            <br />
            <span
              class="font-grotesk uppercase tracking-[.12em] text-[1rem] md:text-[1.35rem] leading-[2rem]"
              >Express your interest</span
            >
          </p>
        </div>

        <div
          class="mb-3 md:mb-4 max-w-lg transition-all duration-1000 delay-500"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        >
          <p class="text-white text-[.9rem] md:text-[1.1rem]">
            to be among the first to receive<br />information about the project
          </p>
        </div>

        <MailchimpForm
          class="transition-all duration-1000 delay-700"
          :class="{
            'opacity-100 translate-y-0': contentVisible,
            'opacity-0 translate-y-1': !contentVisible,
          }"
        ></MailchimpForm>

        <div class="logo mb-1">
          <img class="max-w-30" src="../assets/img/mered.svg" alt="" />
        </div>
      </section>
    </div>

    <div
      class="img-background transition-all duration-5000 delay-500"
      :class="{
        'scale-100 translate-y-0': contentVisible,
        'scale-102 translate-y-0': !contentVisible,
      }"
    ></div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from "vue";
const imageLoaded = ref(false);
const backgroundUrl = "/img/background.jpg";
const contentVisible = ref(false);

onMounted(() => {
  const img = new Image();
  img.src = backgroundUrl;
  img.onload = () => {
    imageLoaded.value = true;
    setTimeout(() => (contentVisible.value = true), 300);
  };
});
</script>

<style scoped>
.landing-index {
  height: 100vh;
  position: relative;
  overflow-y: scroll;
  overflow-x: hidden;
}

.content-container {
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  position: absolute;
  overflow-y: scroll;
  overflow-x: hidden;
  z-index: 1;
}

.img-background {
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  position: absolute;
  background-image: linear-gradient(rgba(0, 0, 0, 0.827), rgba(0, 0, 0, 0.5)),
    url("/img/background.jpg");
  background-position: center center;
  background-size: cover;
}
</style>