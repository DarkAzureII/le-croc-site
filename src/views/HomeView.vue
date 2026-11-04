<script setup lang="ts">
import { ref, computed } from 'vue'

const serviceOptions = [
  { id: 'tyres', name: 'Tyre Fitment & Punctures', short: 'TYRES & PUNCTURES', desc: 'New & old tyre fitment, emergency puncture repairs.' },
  { id: 'mechanical', name: 'Engine Mechanical & Electrical', short: 'ENGINE & GEARBOX', desc: 'Comprehensive engine repairs, overhauls, and electrical system diagnostics.' },
  { id: 'diagnostics', name: 'Full Service Diagnostics', short: 'DIAGNOSTICS', desc: 'Advanced electronic scanning and multi-system fault detection across all makes.' },
] as const

type ServiceCategory = (typeof serviceOptions)[number]['id']

const selectedCategory = ref<ServiceCategory>('tyres')
const vehicleType = ref('Sedan / Hatchback')
const userNote = ref('')

const activeServiceDetails = computed(() => {
  return serviceOptions.find(s => s.id === selectedCategory.value) ?? serviceOptions[0]
})

function handleQuickEnquiry() {
  const serviceName = activeServiceDetails.value?.name ?? 'Automotive Service'
  const message = encodeURIComponent(
    `Hi La'Croc, I need assistance with ${serviceName} for my ${vehicleType.value}. Note: ${userNote.value || 'None'}`
  )
  window.open(`https://wa.me/27729734018?text=${message}`, '_blank')
}

const year = computed(() => new Date().getFullYear())
</script>

<template>
  <div class="relative min-h-screen bg-[#0d0e11] text-neutral-100 selection:bg-red-600 selection:text-white overflow-x-hidden">

    <!-- Top Operational Bar -->
    <div class="border-b border-neutral-800/80 bg-neutral-950/90 px-4 py-2 text-xs text-neutral-400 backdrop-blur-sm sm:px-8 lg:px-20">
      <div class="mx-auto flex max-w-7xl items-center justify-between gap-3 flex-wrap">
        <div class="flex items-center gap-2.5 sm:gap-3 flex-wrap">
          <span class="inline-flex items-center gap-1.5 text-emerald-400 font-semibold text-[11px] sm:text-xs">
            <span class="size-2 rounded-full bg-emerald-500 animate-pulse" />
            WORKSHOP OPEN · CLOSES 17:30
          </span>
          <span class="text-neutral-700 hidden sm:inline">|</span>
          <span class="font-mono text-neutral-300 text-[10px] sm:text-xs hidden md:inline">
            SNOEKFISHMALATJI PROJECTS PTY LTD (REG NO.: 2019/163665/07)
          </span>
        </div>
        <div class="flex items-center gap-4">
          <a href="tel:0729734018" class="text-neutral-300 hover:text-red-400 font-bold transition text-xs sm:text-sm">
            CALL: 072 973 4018
          </a>
        </div>
      </div>
    </div>

    <!-- Hero Section with Industrial Atmosphere -->
    <section class="relative isolate overflow-hidden border-b border-neutral-800/80">
      
      <!-- Workshop Environment Texture & Red Glow Overlays -->
      <div class="absolute inset-0 -z-30 overflow-hidden pointer-events-none">
        <img
          src="https://images.unsplash.com/photo-1597589827317-4c6d6e0a90bd?q=80&w=1600&auto=format&fit=crop"
          alt=""
          class="h-full w-full object-cover opacity-10 filter contrast-125"
        />
        <div class="absolute inset-0 bg-gradient-to-b md:bg-gradient-to-r from-[#0d0e11] via-[#0d0e11]/90 to-transparent" />
        <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_85%_15%,rgba(220,38,38,0.22),transparent_60%)]" />
        <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_15%_90%,rgba(0,0,0,0.8),transparent_70%)]" />
      </div>

      <div class="mx-auto grid max-w-7xl items-center gap-10 px-4 py-12 sm:px-8 sm:py-20 lg:grid-cols-12 lg:gap-14 lg:px-20 lg:py-28">

        <!-- Left Column: Command & Identity -->
        <div class="lg:col-span-7">
          <div class="inline-flex items-center gap-2 px-3 py-1 mb-5 sm:mb-6 border border-neutral-700/80 bg-neutral-900/60 rounded-full text-neutral-300 text-[10px] sm:text-[11px] font-bold tracking-wider uppercase">
            <span class="size-1.5 rounded-full bg-red-500" />
            AUTOMOTIVE HEALTH & DIAGNOSTICS · NTSIMA
          </div>

          <!-- Hero Typography with Responsive Slits SVG -->
<!-- Hero Typography with Responsive Slits SVG -->
          <h1 class="text-4xl font-black italic tracking-tighter leading-[1.05] sm:text-7xl lg:text-8xl flex flex-wrap items-center gap-x-3 sm:gap-x-5">
            <span class="pr-1">Keep You</span>
            
            <!-- Nudged up slightly with -translate-y-[2px] -->
            <span class="relative inline-flex items-center -translate-y-[1px] sm:translate-y-0.7 ml-0.5 sm:ml-2">
              <!-- Back Glow -->
              <span class="absolute inset-0 blur-lg bg-red-600/40 -z-10"></span>
              
              <svg class="h-[0.88em] w-auto max-w-[220px] sm:max-w-none overflow-visible select-none" viewBox="0 0 330 80">
                <defs>
                  <linearGradient id="movingGrad" x1="0%" y1="0%" x2="0%" y2="100%">
                    <stop offset="0%" stop-color="#ff3b53" />
                    <stop offset="45%" stop-color="#dc2626" />
                    <stop offset="100%" stop-color="#6b0714" />
                  </linearGradient>

                  <mask id="cutMask">
                    <rect width="100%" height="100%" fill="white" />
                    <line x1="0" y1="56" x2="350" y2="56" stroke="black" stroke-width="2.5" />
                    <line x1="0" y1="61" x2="350" y2="61" stroke="black" stroke-width="2" />
                  </mask>
                </defs>

                <text
                  x="8"
                  y="74"
                  fill="url(#movingGrad)"
                  font-weight="900"
                  font-style="italic"
                  letter-spacing="-0.04em"
                  font-size="78"
                  font-family="inherit"
                  mask="url(#cutMask)"
                >
                  MOVING
                </text>
              </svg>
            </span>

            <span class="w-full -mt-1 sm:-mt-4 lg:-mt-3">Always!</span>
          </h1>

          <p class="mt-4 sm:mt-6 max-w-xl text-sm leading-relaxed text-neutral-300 sm:text-lg">
            Professional tyre care, gearbox rebuilds, and electrical diagnostics on 1 Sir La'Croc Avenue. Select your service to connect instantly.
          </p>

          <div class="mt-7 sm:mt-8 flex flex-col sm:flex-row items-stretch sm:items-center gap-3 sm:gap-4">
            <a
              href="tel:0729734018"
              class="inline-flex min-h-12 items-center justify-center gap-2.5 bg-red-600 px-6 py-3.5 text-xs font-black uppercase tracking-wider text-white transition hover:bg-red-500 shadow-xl shadow-red-950/60"
            >
              <span>📞 CALL WORKSHOP</span>
              <span class="font-mono">072 973 4018</span>
            </a>

            <a
              href="#services"
              class="inline-flex min-h-12 items-center justify-center border border-neutral-700 bg-neutral-900/70 px-6 py-3.5 text-xs font-bold uppercase tracking-wider text-neutral-200 transition hover:border-red-500 hover:text-white"
            >
              Explore Services
            </a>
          </div>
        </div>

        <!-- Right Column: AutoTrader Quick-Finder Console -->
        <div class="lg:col-span-5 relative mt-6 lg:mt-0">

          <!-- Ambient Split-Glow Fog Layer (Red left to Yellow right) -->
          <div 
            class="pointer-events-none absolute -inset-3 -z-10 rounded-2xl bg-gradient-to-r from-red-600/35 via-rose-500/20 to-amber-400/30 opacity-80 blur-2xl sm:blur-3xl sm:-inset-5 sm:blur-[70px]"
            aria-hidden="true"
          />

          <!-- The outer card WITHOUT overflow-hidden -->
          <div class="relative border border-neutral-800 bg-[#121318]/95 p-5 sm:p-8 shadow-2xl backdrop-blur-md">
            
            <!-- Quick Finder Pill Badge -->
            <div class="absolute -top-3 right-5 sm:right-6 bg-red-600 text-white text-[9px] sm:text-[10px] font-black uppercase tracking-widest px-2.5 sm:px-3 py-1">
              Quick Finder
            </div>

            <!-- Unconstrained Mascot Watermark breaking through the boundaries safely -->
            <div class="pointer-events-none absolute -right-16 sm:-right-44 top-1/2 -translate-y-1/2 z-0 h-[340px] w-[340px] sm:h-[680px] sm:w-[680px] select-none opacity-20 mix-blend-screen filter grayscale">
              <img
                src="@/assets/Croc_Image.png"
                alt=""
                class="h-full w-full object-contain"
                @error="($event.target as HTMLElement).style.display = 'none'"
              />
            </div>

            <!-- Form Content (Elevated above the watermark) -->
            <div class="relative z-10">
              <h2 class="text-lg sm:text-xl font-black tracking-tight text-white uppercase italic">
                QUICK FINDER
              </h2>

              <!-- Category Segmented Control -->
              <div class="mt-4 sm:mt-5 flex flex-wrap gap-1.5 border-b border-neutral-800 pb-3 sm:pb-4">
                <button
                  v-for="s in serviceOptions"
                  :key="s.id"
                  type="button"
                  @click="selectedCategory = s.id"
                  class="px-2 py-1 sm:px-2.5 sm:py-1.5 text-[9px] sm:text-[10px] font-bold tracking-wider uppercase transition rounded-sm"
                  :class="selectedCategory === s.id
                    ? 'border-b-2 border-red-500 text-red-400 bg-red-950/30'
                    : 'text-neutral-400 hover:text-neutral-200'"
                >
                  [{{ s.short }}]
                </button>
              </div>

              <!-- Input Form -->
              <div class="mt-4 sm:mt-5 space-y-3.5 sm:space-y-4 text-xs">
                <div>
                  <label for="vehicleType" class="block font-semibold text-neutral-300 mb-1">
                    Vehicle Type:
                  </label>
                  <select
                    id="vehicleType"
                    v-model="vehicleType"
                    class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3 py-2 sm:px-3.5 sm:py-2.5 text-neutral-200 outline-none focus:border-red-500 rounded-none text-xs sm:text-sm"
                  >
                    <option value="Sedan / Hatchback">Sedan / Hatchback</option>
                    <option value="SUV / 4x4">SUV / 4x4</option>
                    <option value="Bakkie / Commercial">Bakkie / Commercial</option>
                    <option value="Other Vehicle">Other Vehicle</option>
                  </select>
                </div>

                <div>
                  <label for="userNote" class="block font-semibold text-neutral-300 mb-1">
                    Issue Description / Note:
                  </label>
                  <input
                    id="userNote"
                    v-model="userNote"
                    type="text"
                    placeholder="e.g. Puncture repair / Engine shaking"
                    class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3 py-2 sm:px-3.5 sm:py-2.5 text-neutral-200 outline-none placeholder:text-neutral-600 focus:border-red-500 rounded-none text-xs sm:text-sm"
                  />
                </div>

                <div class="pt-2">
                  <button
                    type="button"
                    @click="handleQuickEnquiry"
                    class="w-full inline-flex min-h-11 items-center justify-center gap-2 bg-red-600 px-4 py-3 text-xs font-black tracking-wider uppercase text-white transition hover:bg-red-500 shadow-lg shadow-red-950/50"
                  >
                    <span>SEND ENQUIRY VIA WHATSAPP</span>
                    <span aria-hidden="true">↗</span>
                  </button>
                </div>

                <p class="text-[10px] sm:text-[11px] text-neutral-400 text-center pt-1">
                  Immediate assistance available during operational hours.
                </p>
              </div>
            </div>

          </div>
        </div>

      </div>
    </section>

    <!-- Core Workshop Expertise Cards -->
    <section id="services" class="border-b border-neutral-800/80 bg-neutral-950/60 py-16 sm:py-24">
      <div class="mx-auto max-w-7xl px-4 sm:px-8 lg:px-20">
        <div>
          <h2 class="text-xl sm:text-3xl font-black italic tracking-tight text-white uppercase">
            Workshop Expertise
          </h2>
        </div>

        <div class="mt-8 grid gap-4 sm:gap-5 grid-cols-1 sm:grid-cols-2 lg:grid-cols-4">
          <div class="border border-neutral-800 bg-[#121318] p-5 sm:p-6 hover:border-red-600/60 transition group relative overflow-hidden">
            <span class="text-xs font-mono font-bold text-red-500">01 /</span>
            <h3 class="mt-2 text-base font-black uppercase text-white group-hover:text-red-400 transition">
              TYRES
            </h3>
            <p class="mt-1 text-xs text-neutral-400">
              New & Old Tyre Fitment
            </p>
          </div>

          <div class="border border-neutral-800 bg-[#121318] p-5 sm:p-6 hover:border-red-600/60 transition group relative overflow-hidden">
            <span class="text-xs font-mono font-bold text-red-500">02 /</span>
            <h3 class="mt-2 text-base font-black uppercase text-white group-hover:text-red-400 transition">
              PUNCTURES
            </h3>
            <p class="mt-1 text-xs text-neutral-400">
              Tyre Puncture Repair
            </p>
          </div>

          <div class="border border-neutral-800 bg-[#121318] p-5 sm:p-6 hover:border-red-600/60 transition group relative overflow-hidden">
            <span class="text-xs font-mono font-bold text-red-500">03 /</span>
            <h3 class="mt-2 text-base font-black uppercase text-white group-hover:text-red-400 transition">
              MECHANICAL
            </h3>
            <p class="mt-1 text-xs text-neutral-400">
              Engine & Gearbox Repair
            </p>
          </div>

          <div class="border border-neutral-800 bg-[#121318] p-5 sm:p-6 hover:border-red-600/60 transition group relative overflow-hidden">
            <span class="text-xs font-mono font-bold text-red-500">04 /</span>
            <h3 class="mt-2 text-base font-black uppercase text-white group-hover:text-red-400 transition">
              DIAGNOSTICS
            </h3>
            <p class="mt-1 text-xs text-neutral-400">
              Full Service Diagnostics
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Operational Hours & Location Section with Interactive Google Map -->
    <section class="border-t border-neutral-800/80 bg-neutral-900/40 py-14 sm:py-24">
      <div class="mx-auto max-w-7xl px-4 sm:px-8 lg:px-20">
        <div class="mb-8 sm:mb-10">
          <p class="text-[11px] sm:text-xs font-bold uppercase tracking-[0.22em] text-red-600">
            Find Us on the Map
          </p>
          <h2 class="mt-2 sm:mt-3 text-2xl font-black tracking-tight sm:text-4xl text-white">
            Workshop Location & Working Hours
          </h2>
        </div>

        <div class="grid gap-6 sm:gap-8 lg:grid-cols-12 items-stretch">
          <!-- Information Column -->
          <div class="lg:col-span-5 flex flex-col justify-between border border-neutral-800 bg-neutral-900 p-6 sm:p-8">
            <div class="space-y-6 sm:space-y-8">
              <div>
                <span class="text-xs font-mono font-bold uppercase tracking-wider text-red-500">
                  Physical Workshop
                </span>
                <h3 class="mt-1.5 text-lg sm:text-xl font-bold text-white">
                  1 Sir La'Croc Avenue
                </h3>
                <p class="mt-1 text-xs sm:text-sm text-neutral-400">
                  Ntsima, Limpopo, 0711
                </p>
                <p class="mt-2.5 text-xs leading-relaxed text-neutral-500">
                  Equipped tyre fitment bays, heavy hydraulic jacks, and OBD-II electronic diagnostic station on site.
                </p>
              </div>

              <div class="border-t border-neutral-800 pt-5 sm:pt-6">
                <span class="text-xs font-mono font-bold uppercase tracking-wider text-red-500">
                  Trading Schedule
                </span>
                <ul class="mt-3 space-y-2 text-xs text-neutral-300">
                  <li class="flex items-center justify-between border-b border-neutral-800/60 pb-2">
                    <span class="font-medium">Monday – Saturday</span>
                    <span class="font-mono text-neutral-200">07:30 – 17:30</span>
                  </li>
                  <li class="flex items-center justify-between pt-1">
                    <span class="font-medium text-red-400">Sundays & Holidays</span>
                    <span class="font-mono text-red-400">08:30 – 13:00</span>
                  </li>
                </ul>
              </div>
            </div>

            <div class="mt-6 sm:mt-8 pt-5 sm:pt-6 border-t border-neutral-800 flex flex-col sm:flex-row gap-2.5 sm:gap-3">
              <a
                href="https://www.google.com/maps/search/?api=1&query=1+Sir+La'Croc+Avenue+Ntsima+0711"
                target="_blank"
                rel="noopener noreferrer"
                class="inline-flex flex-1 items-center justify-center gap-2 bg-red-600 px-4 py-3 text-xs font-bold text-white transition hover:bg-red-500 shadow-md shadow-red-950/40"
              >
                <span>Open in Google Maps</span>
                <span aria-hidden="true">↗</span>
              </a>
              <a
                href="tel:0729734018"
                class="inline-flex items-center justify-center border border-neutral-700 bg-neutral-950 px-4 py-3 text-xs font-semibold text-neutral-300 transition hover:border-red-500 hover:text-white"
              >
                <span>Call Ahead</span>
              </a>
            </div>
          </div>

          <!-- Embedded Map Column -->
          <div class="lg:col-span-7 relative min-h-[300px] sm:min-h-[360px] lg:min-h-full overflow-hidden border border-neutral-800 bg-neutral-900">
            <iframe
              title="La'Croc Workshop Location Map"
              width="100%"
              height="100%"
              style="border:0;"
              loading="lazy"
              allowfullscreen
              referrerpolicy="no-referrer-when-downgrade"
              src="https://maps.google.com/maps?q=1%20Sir%20La'Croc%20Avenue,%20Ntsima,%200711&t=&z=14&ie=UTF8&iwloc=&output=embed"
              class="absolute inset-0 h-full w-full invert hue-rotate-180 contrast-90 opacity-90 transition duration-300 hover:opacity-100"
            />
            
            <div class="absolute bottom-3 left-3 sm:bottom-4 sm:left-4 z-10 border border-neutral-800 bg-neutral-950/90 px-3 py-1.5 text-[10px] sm:text-[11px] font-medium text-neutral-300 backdrop-blur-sm pointer-events-none">
              📍 <strong class="text-white">La'Croc Tyre Health Center</strong> · Ntsima
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Page Footer -->
    <div class="border-t border-neutral-800 bg-neutral-900/90 px-4 py-6 text-center text-xs text-neutral-500 sm:px-8 pb-20 md:pb-6">
      © {{ year }} Snoekfishmalatji Projects Pty Ltd (Reg No.: 2019/163665/07) t/a La'Croc Tyre Health Center and Mechanical Services.
    </div>

    <!-- Sticky Mobile Conversion Drawer -->
    <div class="md:hidden fixed bottom-0 inset-x-0 z-50 border-t border-neutral-800 bg-neutral-950/95 p-3 backdrop-blur-lg flex gap-2">
      <a
        href="tel:0729734018"
        class="flex-1 inline-flex items-center justify-center gap-1.5 bg-neutral-900 border border-neutral-700 py-2.5 text-xs font-bold text-white uppercase tracking-wider"
      >
        <span>📞 Call</span>
      </a>
      <button
        type="button"
        @click="handleQuickEnquiry"
        class="flex-1 inline-flex items-center justify-center gap-1.5 bg-red-600 py-2.5 text-xs font-black text-white uppercase tracking-wider shadow-lg shadow-red-950/50"
      >
        <span>WhatsApp ↗</span>
      </button>
    </div>

  </div>
</template>