<template>
  <main
    class="flex flex-col items-center w-screen overflow-x-hidden font-sans bg-primary-50 h-fit"
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
      class="flex items-center justify-center w-screen h-screen bg-gradient-to-t from-primary-100/50 to-primary-50"
    >
      <div
        :style="{ transform: `translateX(${-translate}px) skewX(12deg)` }"
        class="absolute w-1/6 h-full skew-x-12 pointer-events-none left-1/3 bg-primary-400/30"
      />
      <div class="flex items-center">
        <article class="flex flex-col items-end w-[600px]">
          <h1 class="italic font-extrabold text-7xl text-primary-950">
            This website is kind of portfolio for this guy (literally me)
          </h1>
          <svg
            class="w-fit"
            xmlns="http://www.w3.org/2000/svg"
            width="350"
            height="150"
            viewBox="0 0 24 24"
          >
            <g
              fill="none"
              stroke="currentColor"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="1.5"
            >
              <path d="M17 10h4v4" />
              <path
                d="M3 12c.887-1.284 2.48-2.033 4-2c1.52-.033 3.113.716 4 2s2.48 2.033 4 2c1.52.033 3-1 4-2l2-2"
              />
            </g>
          </svg>
        </article>
        <div
          class="w-[400px] neon-light bg-[url('/img/me2.jpg')] bg-primary-950 border-2 border-primary-700 bg-no-repeat bg-cover bg-center h-[600px] rounded-xl"
        ></div>
      </div>
    </section>

    <section
      class="flex flex-col items-center justify-center w-screen h-screen gap-20 bg-gradient-to-b from-primary-100/50 to-primary-50"
    >
      <div
        :style="{ transform: `translateX(${-translate}px) skewX(-12deg)` }"
        class="absolute w-1/6 h-full pointer-events-none left-1/3 bg-gradient-to-b from-primary-400/30 to-primary-400/30"
      ></div>
      <div
        :style="{ transform: `translateX(${-translate / 4}px) skewX(-12deg)` }"
        class="absolute left-[110%] h-[100%] pointer-events-none bg-primary-400/30 w-1/6"
      />
      <h1 class="font-bold text-center text-8xl text-primary-950">
        These are my projects
      </h1>
      <div class="flex w-1/2 gap-1 h-1/2">
        <div
          :class="
            chosen == 0 ? 'flex-grow shadow-xl border-primary-500' : 'w-[10%]'
          "
          @click="chosen = 0"
          class="w-[10%] h-full bg-gradient-to-t from-primary-300/90 to-primary-200 cursor-pointer transition-all duration-300 border-2 border-primary-300 rounded-lg"
        >
          <div class="relative flex flex-col items-center p-2 py-6">
            <NuxtImg
              class="w-1/2"
              src="https://s3.dualstack.us-east-2.amazonaws.com/pythondotorg-assets/media/community/logos/python-logo-only.png"
            />
          </div>
        </div>

        <div
          @click="chosen = 2"
          :class="
            chosen == 2 ? 'flex-grow shadow-xl border-primary-500' : 'w-[10%]'
          "
          class="w-[10%] h-full bg-gradient-to-t from-primary-300/90 to-primary-200 cursor-pointer transition-all duration-300 border-2 border-primary-300 rounded-lg"
        ></div>
        <div
          @click="chosen = 3"
          :class="
            chosen == 3 ? 'flex-grow shadow-xl border-primary-500' : 'w-[10%]'
          "
          class="w-[10%] h-full bg-gradient-to-t from-primary-300/90 to-primary-200 cursor-pointer transition-all duration-300 rounded-lg border-2 border-primary-300"
        ></div>
        <div
          @click="chosen = 4"
          :class="
            chosen == 4 ? 'flex-grow shadow-xl border-primary-500' : 'w-[10%]'
          "
          class="w-[10%] h-full bg-gradient-to-t from-primary-300/90 to-primary-200 cursor-pointer transition-all duration-300 rounded-lg border-2 border-primary-300"
        ></div>
      </div>
    </section>
  </main>
</template>
<style scoped>
.neon-light {
  box-shadow: 0 0 40px #51c2ba;
}
</style>
<script setup>
import { onMounted, onUnmounted } from "vue";

let translate = ref(0);

let chosen = ref(0);

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
