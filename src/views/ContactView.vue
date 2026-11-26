<template>
  <!-- EXPERIENCE & CAREER -->
  <section class="flex w-full flex-col items-stretch bg-black lg:flex-row">
    <!-- LEFT: EXPERIENCE -->
    <div class="w-full bg-gray-100 lg:w-[52%]">
      <div id="experience" class="w-full scroll-mt-20 px-6 py-10 sm:px-10 lg:px-12 lg:py-12">
        <!-- Heading -->
        <div class="mb-8">
          <p class="mb-2 text-sm font-bold text-blue-500">My Journey</p>

          <h2 class="text-2xl font-bold tracking-tight text-slate-950 sm:text-3xl">
            Work Experience & Education
          </h2>

          <p class="mt-3 pb-5 text-sm leading-6 text-slate-500">
            My professional journey through software development, engineering and continuous
            learning.
          </p>
        </div>

        <!-- Timeline -->
        <div class="relative">
          <div
            v-for="(experience, index) in experiences"
            :key="experience.id"
            class="relative flex gap-4 pb-7 last:pb-0"
          >
            <!-- Timeline Line & Dot -->
            <div class="relative flex w-4 shrink-0 justify-center">
              <div
                v-if="index !== experiences.length - 1"
                class="absolute top-4 -bottom-7 w-0.5 bg-indigo-200"
              ></div>

              <div
                class="relative z-10 mt-1 h-3.5 w-3.5 rounded-full border-[3px] border-indigo-500 bg-white"
                :class="experience.current ? 'bg-indigo-500 ring-4 ring-indigo-100' : ''"
              ></div>
            </div>

            <!-- Experience Content -->
            <div class="min-w-0 flex-1">
              <div class="flex flex-wrap items-start justify-between gap-2">
                <div>
                  <h3 class="text-sm font-bold text-slate-900 sm:text-base">
                    {{ experience.role }}
                  </h3>

                  <div class="mt-1 flex flex-wrap items-center gap-2">
                    <span class="text-sm font-medium text-indigo-600">
                      {{ experience.company }}
                    </span>

                    <span
                      v-if="experience.familyBusiness"
                      class="rounded bg-indigo-50 px-2 py-0.5 text-[10px] font-medium text-indigo-700"
                    >
                      Family Business
                    </span>
                  </div>
                </div>

                <BaseBadge :text="experience.period" variant="primary" size="sm" />
              </div>

              <!-- Single Description -->
              <p class="mt-2 text-sm leading-6 text-slate-500">
                {{ experience.description }}
              </p>

              <!-- Current Role -->
              <div v-if="experience.current" class="mt-2 flex items-center gap-2">
                <span class="h-1.5 w-1.5 rounded-full bg-emerald-500"></span>

                <span class="text-xs font-medium text-emerald-700"> Current Position </span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- RIGHT: CAREER OPPORTUNITIES -->
    <div class="flex w-full flex-col justify-center gap-8 bg-black p-6 sm:p-10 lg:w-[48%] lg:p-12">
      <!-- Heading -->
      <div class="flex flex-col gap-3">
        <p class="text-sm font-bold text-blue-500">What's Next?</p>

        <h2 class="max-w-xl text-2xl font-bold leading-tight text-white sm:text-3xl">
          Looking for a Developer to Join Your Team?
        </h2>

        <p class="mt-2 max-w-xl text-sm leading-7 text-gray-400">
          Having progressed from Junior PHP Developer to Intermediate Software Developer, I've
          gained hands-on experience building and maintaining real-world applications. I'm now
          seeking a permanent opportunity to contribute my skills, collaborate with a development
          team and continue growing professionally.
        </p>
      </div>

      <!-- Technical Expertise -->
      <div class="flex flex-col gap-4 border-t border-white/10 pt-6">
        <h3 class="text-lg font-semibold text-white">Technical Expertise</h3>

        <div class="grid grid-cols-1 gap-3 sm:grid-cols-3 lg:grid-cols-1 xl:grid-cols-3">
          <div
            v-for="expertise in expertiseItems"
            :key="expertise.title"
            class="flex flex-col gap-3 rounded-lg border border-white/10 bg-gray-900/60 p-4"
          >
            <Icon :icon="expertise.icon" class="text-2xl text-blue-400" />

            <div class="flex flex-col gap-1">
              <h4 class="text-sm font-semibold text-white">
                {{ expertise.title }}
              </h4>

              <p class="text-xs leading-5 text-gray-400">
                {{ expertise.description }}
              </p>
            </div>
          </div>
        </div>
      </div>

      <!-- Availability -->
      <div class="flex items-center gap-2">
        <span class="h-2 w-2 rounded-full bg-emerald-500"></span>

        <p class="text-xs leading-5 text-gray-500">
          Interested in frontend, backend and full-stack software development positions.
        </p>
      </div>

      <!-- CTA -->
      <div class="flex flex-wrap items-center gap-4">
        <BaseButton to="/contact" variant="hero" size="lg">
          <span class="flex items-center gap-2">
            Discuss an Opportunity
            <PhArrowRight :size="18" weight="bold" />
          </span>
        </BaseButton>

        <a
          href="https://www.linkedin.com/in/abdul-azeez-kemp-3b468121a/"
          target="_blank"
          rel="noopener noreferrer"
          class="flex items-center gap-2 text-sm font-medium text-gray-300 transition-colors hover:text-blue-400"
        >
          <PhLinkedinLogo :size="20" weight="bold" />
          View LinkedIn
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { PhArrowRight, PhLinkedinLogo } from '@phosphor-icons/vue'

import { Icon } from '@iconify/vue'

const experiences = [
  {
    id: 1,
    role: 'Fitter & Turner',
    company: 'Moegsien Projects',
    period: '2026 – Present',
    current: true,
    familyBusiness: true,
    description:
      'Returned to the family business, contributing to mechanical engineering, machining and manufacturing while pursuing my software development career.',
  },
  {
    id: 2,
    role: 'Intermediate Software Developer',
    company: 'FutureRent',
    period: 'Nov 2025 – Jul 2026',
    current: false,
    familyBusiness: false,
    description:
      'Developed and maintained full-stack web applications using PHP, Vue.js and MySQL. Built business workflows, API integrations, automated notifications and internal management tools.',
  },
  {
    id: 3,
    role: 'Junior PHP Developer',
    company: 'FutureRent',
    period: 'Nov 2024 – Nov 2025',
    current: false,
    familyBusiness: false,
    description:
      'Developed PHP-based applications, implemented new features and worked with MySQL databases. Collaborated with the development team to improve existing systems and functionality.',
  },
  {
    id: 4,
    role: 'Fitter & Turner',
    company: 'Moegsien Projects',
    period: 'Oct 2023 – Nov 2024',
    current: false,
    familyBusiness: true,
    description:
      'Worked in precision machining and mechanical manufacturing, developing practical technical skills, attention to detail and problem-solving abilities.',
  },
  {
    id: 5,
    role: 'Software Development Training',
    company: 'Life Choices Academy',
    period: 'Sep 2022 – Dec 2023',
    current: false,
    familyBusiness: false,
    description:
      'Completed a one-year full-stack software development programme in September 2023, gaining practical experience in frontend and backend development. Remained with the academy until December.',
  },
]

const expertiseItems = [
  {
    title: 'Frontend',
    icon: 'ph:browser',
    description:
      'Building responsive, interactive interfaces with Vue.js, JavaScript, HTML, CSS and Tailwind CSS.',
  },
  {
    title: 'Backend',
    icon: 'ph:database',
    description:
      'Developing PHP applications, MySQL database solutions, REST APIs and system integrations.',
  },
  {
    title: 'Development Tools',
    icon: 'ph:code',
    description:
      'Using Git, Docker and VS Code to manage code, development environments and project workflows.',
  },
]
</script>
