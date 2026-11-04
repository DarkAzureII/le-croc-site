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
    <header class="sticky top-0 z-50 border-b border-neutral-800 bg-neutral-950/95 backdrop-blur-md">
      <div class="mx-auto flex max-w-7xl items-center justify-between px-4 py-3 sm:px-8 sm:py-4 lg:px-20">
        
        <!-- Logo & Branding -->
        <RouterLink
          to="/"
          class="flex items-center gap-2.5 sm:gap-3.5 group shrink-0"
          aria-label="La'Croc Tyre Health Center and Mechanical Services home"
          @click="closeMenu"
        >
          <div class="relative flex h-9 sm:h-10 max-w-[120px] sm:max-w-[140px] items-center justify-center">
            <img 
              src="@/assets/logo.png" 
              alt="La'Croc Logo" 
              class="max-h-9 sm:max-h-10 w-auto object-contain"
              @error="($event.target as HTMLElement).style.display = 'none'"
            />
          </div>

          <span class="flex flex-col">
            <span class="text-base sm:text-lg font-black italic tracking-tighter uppercase text-white group-hover:text-red-500 transition drop-shadow-sm leading-tight">
              <span class="text-white">LA'</span><span class="text-red-600">CROC</span>
            </span>
            <span class="text-[8px] sm:text-[9px] tracking-[0.18em] text-neutral-400 font-semibold uppercase">
              Tyre Health & Mechanical
            </span>
          </span>
        </RouterLink>

        <!-- Desktop Navigation -->
        <nav class="hidden md:flex md:items-center md:gap-8">
          <RouterLink
            to="/"
            class="text-sm font-semibold tracking-wide text-neutral-300 transition hover:text-red-500"
          >
            Home
          </RouterLink>

          <RouterLink
            to="/about"
            class="text-sm font-semibold tracking-wide text-neutral-300 transition hover:text-red-500"
          >
            About
          </RouterLink>

          <RouterLink
            to="/contact"
            class="bg-red-600 px-5 py-2.5 text-xs font-black uppercase tracking-wider text-white transition hover:bg-red-500 shadow-lg shadow-red-950/50"
          >
            Contact Us
          </RouterLink>
        </nav>

        <!-- Mobile 3-Line Hamburger Button -->
        <button
          type="button"
          class="relative flex h-10 w-10 flex-col items-center justify-center gap-1.5 rounded-lg border border-neutral-800 bg-neutral-900/80 p-2 text-neutral-300 transition hover:border-red-500/60 hover:text-white focus:outline-none md:hidden"
          :aria-expanded="menuOpen"
          aria-controls="mobile-navigation"
          :aria-label="menuOpen ? 'Close navigation' : 'Open navigation'"
          @click="menuOpen = !menuOpen"
        >
          <!-- Line 1 -->
          <span
            class="h-0.5 w-5 rounded-full bg-current transition-all duration-300 ease-in-out"
            :class="menuOpen ? 'translate-y-2 rotate-45 bg-red-500' : ''"
          />
          <!-- Line 2 -->
          <span
            class="h-0.5 w-5 rounded-full bg-current transition-all duration-200 ease-in-out"
            :class="menuOpen ? 'opacity-0' : 'opacity-100'"
          />
          <!-- Line 3 -->
          <span
            class="h-0.5 w-5 rounded-full bg-current transition-all duration-300 ease-in-out"
            :class="menuOpen ? '-translate-y-2 -rotate-45 bg-red-500' : ''"
          />
        </button>
      </div>

      <!-- Mobile Dropdown Navigation -->
      <transition
        enter-active-class="transition duration-200 ease-out"
        enter-from-class="opacity-0 -translate-y-2"
        enter-to-class="opacity-100 translate-y-0"
        leave-active-class="transition duration-150 ease-in"
        leave-from-class="opacity-100 translate-y-0"
        leave-to-class="opacity-0 -translate-y-2"
      >
        <nav
          v-if="menuOpen"
          id="mobile-navigation"
          class="border-t border-neutral-800 bg-neutral-950/98 px-5 py-4 space-y-2 md:hidden"
        >
          <RouterLink
            to="/"
            class="block rounded-md px-3 py-2.5 text-sm font-semibold tracking-wide text-neutral-200 hover:bg-neutral-900 hover:text-red-400 transition"
            @click="closeMenu"
          >
            Home
          </RouterLink>

          <RouterLink
            to="/about"
            class="block rounded-md px-3 py-2.5 text-sm font-semibold tracking-wide text-neutral-200 hover:bg-neutral-900 hover:text-red-400 transition"
            @click="closeMenu"
          >
            About
          </RouterLink>

          <div class="pt-2">
            <RouterLink
              to="/contact"
              class="block w-full bg-red-600 py-3 text-center text-xs font-black uppercase tracking-wider text-white shadow-lg shadow-red-950/60 transition hover:bg-red-500"
              @click="closeMenu"
            >
              Contact Us
            </RouterLink>
          </div>
        </nav>
      </transition>
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