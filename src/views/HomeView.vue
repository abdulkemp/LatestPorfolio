<template>
  <section
    class="relative isolate flex h-[90vh] w-full flex-row items-center justify-start overflow-hidden text-black sm:px-8 lg:px-10"
    :style="{ backgroundImage: `url(${heroBackground})` }"
  >
    <div class="w-full h-fit ">
      <div class="w-1/2 flex flex-col gap-4 pl-10">
        <h2 class="text-blue-500 text-2xl font-bold">Hello I'm,</h2>
        <h1 class="text-6xl text-white font-bold">
          Abdul Azeez <span class="text-blue-500 font-bold">Kemp</span>
        </h1>
        <h2 class="text-xl font-bold text-white">
          Intermediate Software Developer
        </h2>
        <p class="text-lg w-3/4 text-gray-400">
          I build modern, scalable web applications using PHP, Vue and modern web technologies. I enjoy turning ideas into clean, friendly and user-friendly solutions.
        </p>
        <div class="mt-10 flex items-center gap-x-6">
          <BaseButton
          variant="hero"
            class=" cursor-pointer"
          >
            <RouterLink
              to="/projects"
              class="rounded-md p-1 text-sm font-bold text-white lg:inline-flex w-fit items-center gap-2"
            >
              View My Work <PhArrowRight :size="16" />
            </RouterLink>
          </BaseButton>

          <BaseButton
            variant="ghost"
            class="cursor-pointer border-0"
          >
            <RouterLink
              to="/contact"
              class="rounded-md px-3 py-1 text-sm font-bold text-white lg:inline-flex w-fit items-center gap-2"
            >
              Contact Me <PhArrowRight :size="16" class="text-white"/>
            </RouterLink>
          </BaseButton>
        </div>
      </div>
    </div>
    <!-- <div class="p-4 w-1/2">
      <img
        src="/src/assets/dashboard1.png"
        alt=""
        class="w-full object-contain drop-shadow-[0_10px_10px_rgba(15,23,42,0.28)]"
      />
    </div> -->
  </section>
  <section>
    
  </section>
</template>

<script setup>
import { BaseButton } from "@/components/UI";
import { PhArrowRight } from "@phosphor-icons/vue";
import { RouterLink } from "vue-router";
import heroBackground from '@/assets/hero-background.png'
</script>
