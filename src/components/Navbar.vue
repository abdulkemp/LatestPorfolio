
<template>
  <header
    class="fixed inset-x-0 top-0 z-50 w-full transition-all duration-500 ease-in-out"
    :class="
      isScrolled
        ? 'bg-black shadow-lg shadow-black/10'
        : 'bg-transparent'
    "
  >
    <nav
      class="mx-auto flex h-15 w-full items-center justify-between px-3 sm:px-8 lg:px-10"
    >
      <!-- LOGO -->
      <RouterLink
        to="/"
        class="flex items-center gap-3 text-white"
        aria-label="Go to home section"
      >
        <PhCode :size="28" weight="bold" />

        <span
          class="text-2xl font-bold transition-colors duration-300"
        >
          AAK
        </span>
      </RouterLink>

      <!-- DESKTOP NAVIGATION -->
      <div class="hidden items-center gap-1 md:flex">
        <RouterLink
          v-for="item in navItems"
          :key="item.path"
          :to="item.path"
          class="rounded-md px-4 py-2 text-sm font-bold text-white transition-all duration-300 hover:bg-white/15"
          :class="{
            'bg-white/15': route.path === item.path,
          }"
        >
          {{ item.label }}
        </RouterLink>
      </div>

      <!-- DOWNLOAD CV -->
      <a
        href="/cv.pdf"
        download
        class="hidden w-fit items-center gap-2 rounded-[25px] border-2 border-white bg-transparent px-4 py-2 text-sm font-black text-white shadow-sm shadow-cyan-500/20 transition-all duration-300 hover:bg-white hover:text-black lg:inline-flex"
      >
        Download CV

        <PhDownloadSimple :size="16" />
      </a>

      <!-- MOBILE MENU BUTTON -->
      <button
        type="button"
        class="grid h-10 w-10 place-items-center rounded-md border border-white/50 text-white md:hidden"
        :aria-expanded="isOpen"
        aria-label="Toggle navigation"
        @click="isOpen = !isOpen"
      >
        <PhList :size="24" />
      </button>
    </nav>

    <!-- MOBILE MENU -->
    <div
      v-if="isOpen"
      class="w-full border-t border-white/10 bg-black px-5 py-4 md:hidden"
    >
      <div class="mx-auto grid max-w-7xl gap-2">
        <RouterLink
          v-for="item in navItems"
          :key="item.path"
          :to="item.path"
          class="rounded-md px-4 py-3 text-sm font-bold text-white transition-colors hover:bg-white/10"
          :class="{
            'bg-white/15': route.path === item.path,
          }"
          @click="isOpen = false"
        >
          {{ item.label }}
        </RouterLink>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import { RouterLink, useRoute } from 'vue-router'

import {
  PhCode,
  PhList,
  PhDownloadSimple,
} from '@phosphor-icons/vue'

const route = useRoute()

const isOpen = ref(false)
const isScrolled = ref(false)

// Change navbar background after scrolling
const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

onMounted(() => {
  handleScroll()

  window.addEventListener('scroll', handleScroll, {
    passive: true,
  })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const navItems = [
  { label: 'Home', path: '/' },
  { label: 'About', path: '/about' },
  { label: 'Experience', path: '/experience' },
  { label: 'Projects', path: '/projects' },
  { label: 'Contact', path: '/contact' },
]
</script>
