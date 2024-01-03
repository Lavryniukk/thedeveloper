<template>
  <main
    class="flex bg-primary-50 overflow-x-hidden w-screen h-fit flex-col items-center"
  >
    <section
      class="flex items-center bg-primary-50 justify-center w-screen h-screen"
    >
      <div
        :style="{ transform: `translateX(${-translate}px) skewX(-12deg)` }"
        class="absolute left-1/3 h-full bg-gradient-to-b from-primary-400/10 to-primary-400/30 w-1/6"
      ></div>
      <div
        :style="{ transform: `translateX(${translate / 2}px) skewX(12deg)` }"
        class="absolute left-3/4 skew-x-12 h-full bg-gradient-to-b from-primary-400/10 to-primary-400/30 w-1/6"
      />

      <div></div>
      <h1 class="font-extrabold font-sans text-9xl text-primary-950">
        THE DEVELOPER
      </h1>
    </section>
    <section
      class="h-screen w-screen bg-gradient-to-t from-primary-100/50 to-primary-50"
    >
      <div
        :style="{ transform: `translateX(${-translate}px) skewX(12deg)` }"
        class="absolute left-[38.85%] skew-x-12 h-[200%] bg-primary-400/30 w-1/6"
      />
      <div
        :style="{ transform: `translateX(${translate / 2}px) skewX(12deg)` }"
        class="absolute left-[91.6%] skew-x-12 h-[200%] bg-primary-400/30 w-1/6"
      />
    </section>

    <section class="w-screen h-screen bg-primary-200">
      <div
        :style="{ transform: `translateX(${-translate / 4}px) skewX(-12deg)` }"
        class="absolute left-[110%] h-[100%] bg-primary-400/30 w-1/6"
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
