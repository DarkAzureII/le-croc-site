<script setup lang="ts">
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

const menuOpen = ref(false)

function closeMenu() {
  menuOpen.value = false
}
</script>

<template>
  <div class="flex min-h-screen flex-col bg-neutral-950 text-neutral-100 selection:bg-red-600 selection:text-white">
    <!-- Header -->
    <header
      class="sticky top-0 z-50 flex flex-wrap items-center justify-between gap-4 border-b border-neutral-800 bg-neutral-950/90 px-5 py-4 backdrop-blur-md sm:px-8 lg:px-20"
    >
      <RouterLink
        to="/"
        class="flex items-center gap-3.5 group"
        aria-label="La'Croc Tyre Health Center and Mechanical Services home"
        @click="closeMenu"
      >

        <div class="relative flex h-10 max-w-[140px] items-center justify-center">
          <img 
            src="@/assets/logo.png" 
            alt="La'Croc Logo" 
            class="max-h-10 w-auto object-contain"
            @error="($event.target as HTMLElement).style.display = 'none'"
          />
        </div>

        <span class="flex flex-col gap-0.5">
          <!-- Styled to match that heavy italic racing logo font vibe -->
          <span class="text-lg font-black italic tracking-tighter uppercase text-white group-hover:text-red-500 transition drop-shadow-sm">
            <span class="text-white">LA'</span><span class="text-red-600">CROC</span>
          </span>
          <span class="text-[9px] tracking-[0.2em] text-neutral-400 font-semibold uppercase">
            Tyre Health & Mechanical
          </span>
        </span>
      </RouterLink>

      <!-- Mobile menu toggle -->
      <button
        type="button"
        class="rounded border border-neutral-700 bg-neutral-900 px-4 py-2 text-sm font-semibold text-neutral-200 transition hover:border-red-500 hover:text-red-400 sm:hidden"
        :aria-expanded="menuOpen"
        aria-controls="site-navigation"
        :aria-label="menuOpen ? 'Close navigation' : 'Open navigation'"
        @click="menuOpen = !menuOpen"
      >
        {{ menuOpen ? 'Close' : 'Menu' }}
      </button>

      <!-- Navigation -->
      <nav
        id="site-navigation"
        class="w-full flex-col gap-2 sm:flex sm:w-auto sm:flex-row sm:items-center sm:gap-8"
        :class="menuOpen ? 'flex' : 'hidden sm:flex'"
      >
        <RouterLink
          to="/"
          class="py-3 text-sm font-medium text-neutral-300 transition hover:text-red-500 sm:py-2"
          @click="closeMenu"
        >
          Home
        </RouterLink>

        <RouterLink
          to="/about"
          class="py-3 text-sm font-medium text-neutral-300 transition hover:text-red-500 sm:py-2"
          @click="closeMenu"
        >
          About
        </RouterLink>

        <RouterLink
          to="/contact"
          class="bg-red-600 px-6 py-3 text-center text-sm font-bold text-white transition hover:bg-red-500 shadow-lg shadow-red-950/40 sm:py-2.5"
          @click="closeMenu"
        >
          Contact Us
        </RouterLink>
      </nav>
    </header>

    <!-- Route content -->
    <main class="flex-1">
      <RouterView />
    </main>

    <!-- Footer -->
    <footer
      id="contact"
      class="border-t border-neutral-800 bg-neutral-900/60 px-5 py-12 text-sm text-neutral-400 sm:px-8 lg:px-20"
    >
      <div class="mx-auto grid max-w-7xl gap-8 md:grid-cols-3">
        <div>
          <p class="font-black tracking-wider text-white text-base">
            LA'CROC TYRE HEALTH CENTER
          </p>
          <p class="mt-2 text-xs text-neutral-500">
            Snoekfishmalatji Projects Pty Ltd (Reg No.: 2019/163665/07).
          </p>
          <p class="mt-3 text-xs text-neutral-400 italic">
            "Keep You Moving Always!"
          </p>
        </div>

        <div>
          <p class="font-bold text-neutral-200">Workshop Location</p>
          <p class="mt-2 text-xs leading-relaxed text-neutral-400">
            1 Sir La'Croc Avenue, Ntsima, 0711<br />
            Mon–Sat: 07:30 – 17:30<br />
            Sun & Holidays: 08:30 – 13:00
          </p>
        </div>

        <div>
          <p class="font-bold text-neutral-200">Direct Contact</p>
          <p class="mt-2 text-xs text-neutral-400">
            Phone / WhatsApp: <a href="tel:0729734018" class="text-red-400 font-bold hover:underline">072 973 4018</a><br />
            Email: <a href="mailto:sagaciouskr@gmail.com" class="text-neutral-300 hover:underline">sagaciouskr@gmail.com</a>
          </p>
        </div>
      </div>

      <div class="mx-auto mt-12 max-w-7xl border-t border-neutral-800/80 pt-6 text-center text-xs text-neutral-500">
        © {{ new Date().getFullYear() }} La'Croc Tyre Health Center and Mechanical Services. All rights reserved.
      </div>
    </footer>
  </div>
</template>