<template>
  <section class="w-full h-[50vh] flex flex-row justify-center items-start bg-black">
    <div class="w-[58%] h-full flex flex-row gap-5 p-10 bg-gray-100">
      <div class="w-full h-full flex justify-center items-center flex-col gap-6">
        <div class="w-full h-full gap-5 flex justify-center items-center">
          <div class="w-[65%] h-full flex flex-col gap-3 justify-center items-start">
            <h2 class="text-blue-500 text-lg font-bold">About Me</h2>
            <h1 class="text-4xl font-bold">Building Solutions That Makes A Difference</h1>
            <p class="text-lg text-slate-600">
              I'm an intermediate software developer with 1.5 years of professional experience,
              currently working with PHP, Vue, MySQL and modern web technologies. I enjoy solving
              real-world problems and continuously learning new tools and best practices.
            </p>
          </div>
          <div class="w-[35%] h-60 p-3 flex justify-center items-center">
            <div
              class="w-full h-full bg-cover bg-center rounded-2xl"
              :style="{
                backgroundImage: `url(${aboutme})`,
                backgroundSize: 'cover',
                backgroundPosition: 'center',
              }"
            ></div>
          </div>
        </div>
        <div class="w-full h-full flex justify-start items-start flex-col gap-3">
          <div
            class="grid grid-cols-3 gap-3 md:grid-cols-3 lg:grid-cols-3 xl:grid-cols-4 2xl:grid-cols-4"
          >
            <div
              v-for="about in me"
              :key="about.name"
              class="group flex flex-col w-[190px] items-start justify-start gap-3 rounded-xl border border-black p-3 text-center text-sm font-medium text-black"
            >
              <div class="flex flex-row gap-1 items-center justify-center bg-black rounded-xl p-3">
                <component
                  :is="about.icon"
                  :size="20"
                  weight="duotone"
                  class="shrink-0 text-blue-500"
                />
              </div>
              <div class="flex flex-col gap-1 justify-start items-start">
                <h1 class="font-bolder text-[17px]">{{ about.title }}</h1>
                <p>{{ about.description }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="w-[42%] h-full bg-black flex flex-col justify-start items-start gap-5 p-10">
      <div class="w-full h-full flex flex-col gap-4 justify-center items-center">
        <div class="w-full h-full flex flex-col gap-2 justify-center items-start">
          <h2 class="text-blue-500 text-lg font-bold">Skills</h2>
          <h1 class="text-3xl font-bold text-white">Technologies I Work With</h1>
        </div>
        <div class="w-full h-full flex flex-col gap-5 justify-center items-center border">
          <div
            class="grid grid-cols-2 gap-2 md:grid-cols-3 lg:grid-cols-3 xl:grid-cols-3 2xl:grid-cols-3"
          >
            <div
              v-for="skill in skills"
              :key="skill.name"
              class="group flex flex-col items-center gap-3 rounded-xl border border-white/10 bg-gray-900 p-3 text-center text-sm font-medium text-white"
            >
              <Icon :icon="skill.icon" class="size-10 shrink-0" />

              <span class="font-medium text-white">
                {{ skill.name }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { BaseCard } from '@/components/UI'
import aboutme from '@/assets/about-me.png'
import { Icon } from '@iconify/vue'
// import { locate } from '@iconify/json'
import { PhCode, PhPuzzlePiece, PhRocketLaunch, PhUsersThree } from '@phosphor-icons/vue'

const skills = [
  { name: 'Vue.js', icon: 'logos:vue' },
  { name: 'JavaScript', icon: 'logos:javascript' },
  { name: 'HTML5', icon: 'logos:html-5' },
  { name: 'CSS3', icon: 'logos:css-3' },
  { name: 'PHP', icon: 'logos:php' },
  { name: 'Docker', icon: 'logos:docker-icon' },
  { name: 'Tailwind CSS', icon: 'logos:tailwindcss-icon' },
  { name: 'MySQL', icon: 'logos:mysql' },
]
const me = [
  { name: 'Code', icon: PhCode, title: 'Clean Code', description: 'Maintainable solutions' },
  {
    name: 'Puzzle',
    icon: PhPuzzlePiece,
    title: 'Problem Solving',
    description: 'Turning ideas into reality',
  },
  {
    name: 'Learning',
    icon: PhRocketLaunch,
    title: 'Continuous Learning',
    description: 'Always improving',
  },
  {
    name: 'Team',
    icon: PhUsersThree,
    title: 'Team Collaboration',
    description: 'Effective communication',
  },
]
</script>
