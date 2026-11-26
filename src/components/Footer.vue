
<template>
  <footer
    id="contact"
    class="w-full border-t border-slate-200 bg-white text-slate-950"
  >
    <div
      class="mx-auto flex w-full flex-col gap-8 px-6 py-10 sm:px-10 lg:flex-row lg:items-center lg:justify-between lg:gap-12 lg:px-12"
    >
      <!-- LEFT: INTRODUCTION -->
      <div class="w-full lg:w-[35%]">
        <h2
          class="text-2xl font-bold tracking-tight text-slate-950 sm:text-3xl"
        >
          Get In Touch
        </h2>

        <p class="mt-3 max-w-md text-sm leading-6 text-slate-500">
          I'm open to permanent software development opportunities.
          Feel free to reach out for a chat or to discuss potential roles.
        </p>
      </div>

      <!-- RIGHT: CONTACT CARDS -->
      <div
        class="grid w-full grid-cols-1 gap-4 sm:grid-cols-3 lg:w-[65%]"
      >
        <!-- EMAIL -->
        <a
          href="mailto:aakemp786@gmail.com"
          class="group flex min-w-0 items-center gap-4 rounded-xl border border-slate-200 bg-white p-4 transition-all duration-300 hover:-translate-y-1 hover:border-indigo-300 hover:shadow-lg hover:shadow-indigo-500/10"
        >
          <div
            class="flex h-11 w-11 shrink-0 items-center justify-center rounded-lg bg-indigo-50 text-indigo-600 transition-colors group-hover:bg-indigo-600 group-hover:text-white"
          >
            <PhEnvelopeSimple
              :size="24"
              weight="fill"
            />
          </div>

          <div class="min-w-0">
            <h3 class="text-sm font-bold text-slate-950">
              Email
            </h3>

            <p class="mt-1 truncate text-xs text-slate-500">
              aakemp786@gmail.com
            </p>
          </div>
        </a>

        <!-- LINKEDIN -->
        <a
          href="https://www.linkedin.com/in/abdul-azeez-kemp-3b468121a/"
          target="_blank"
          rel="noopener noreferrer"
          class="group flex min-w-0 items-center gap-4 rounded-xl border border-slate-200 bg-white p-4 transition-all duration-300 hover:-translate-y-1 hover:border-blue-300 hover:shadow-lg hover:shadow-blue-500/10"
        >
          <div
            class="flex h-11 w-11 shrink-0 items-center justify-center rounded-lg bg-blue-50 text-blue-600 transition-colors group-hover:bg-blue-600 group-hover:text-white"
          >
            <PhLinkedinLogo
              :size="24"
              weight="fill"
            />
          </div>

          <div class="min-w-0">
            <h3 class="text-sm font-bold text-slate-950">
              LinkedIn
            </h3>

            <p class="mt-1 truncate text-xs text-slate-500">
              View my profile
            </p>
          </div>
        </a>

        <!-- GITHUB -->
        <a
          href="https://github.com/abdulkemp"
          target="_blank"
          rel="noopener noreferrer"
          class="group flex min-w-0 items-center gap-4 rounded-xl border border-slate-200 bg-white p-4 transition-all duration-300 hover:-translate-y-1 hover:border-slate-400 hover:shadow-lg hover:shadow-slate-500/10"
        >
          <div
            class="flex h-11 w-11 shrink-0 items-center justify-center rounded-lg bg-slate-100 text-slate-900 transition-colors group-hover:bg-slate-900 group-hover:text-white"
          >
            <PhGithubLogo
              :size="24"
              weight="fill"
            />
          </div>

          <div class="min-w-0">
            <h3 class="text-sm font-bold text-slate-950">
              GitHub
            </h3>

            <p class="mt-1 truncate text-xs text-slate-500">
              View my repositories
            </p>
          </div>
        </a>
      </div>
    </div>
  </footer>
</template>

<script setup>
import {
  PhEnvelopeSimple,
  PhLinkedinLogo,
  PhGithubLogo,
} from '@phosphor-icons/vue'
</script>
