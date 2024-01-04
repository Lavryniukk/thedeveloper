<template>
  <main
    class="flex flex-col items-center w-screen overflow-x-hidden bg-primary-50 h-fit"
  >
    <section
      class="flex items-center justify-center w-screen h-screen bg-primary-50"
    >
      <div
        :style="{ transform: `translateX(${-translate}px) skewX(-12deg)` }"
        class="absolute w-1/6 h-full pointer-events-none left-1/3 bg-gradient-to-b from-primary-400/10 to-primary-400/30"
      ></div>
      <div
        :style="{ transform: `translateX(${translate / 2}px) skewX(12deg)` }"
        class="absolute w-1/6 h-[300vh] right-[20%] bg-gradient-to-b pointer-events-none from-primary-400/10 to-primary-400/30"
      />

      <div></div>
      <h1 class="font-sans font-extrabold text-9xl text-primary-950">
        THE DEVELOPER
      </h1>
    </section>
    <section
      class="w-screen h-screen bg-gradient-to-t from-primary-100/50 to-primary-50"
    >
      <div
        :style="{ transform: `translateX(${-translate}px) skewX(12deg)` }"
        class="absolute w-1/6 h-full skew-x-12 pointer-events-none left-1/3 bg-primary-400/30"
      />
    </section>

    <section
      class="w-screen h-screen bg-gradient-to-b from-primary-100/50 to-primary-50"
    >
      <div
        :style="{ transform: `translateX(${-translate}px) skewX(-12deg)` }"
        class="absolute w-1/6 h-full pointer-events-none left-1/3 bg-gradient-to-b from-primary-400/30 to-primary-400/30"
      ></div>
      <div
        :style="{ transform: `translateX(${-translate / 4}px) skewX(-12deg)` }"
        class="absolute left-[110%] h-[100%] pointer-events-none bg-primary-400/30 w-1/6"
      />
    </section>
  </main>
</template>
<script setup>
import { onMounted, onUnmounted } from "vue";
let translate = ref(0);
const handleScroll = () => {
  translate.value = window.scrollY / 2;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
