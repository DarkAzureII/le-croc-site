<script setup lang="ts">
import { ref, computed } from 'vue'

const clientName = ref('')
const clientPhone = ref('')
const vehicleInfo = ref('')
const inquiryType = ref<'emergency' | 'quote' | 'general'>('quote')
const inquiryMessage = ref('')

function handleContactSubmit() {
  const urgencyTag = inquiryType.value === 'emergency' ? '🚨 [URGENT EMERGENCY]' : '[GENERAL / QUOTE]'
  const text = encodeURIComponent(
    `Hi La'Croc Tyre Health Center,\n\n${urgencyTag}\nName: ${clientName.value || 'Not provided'}\nPhone: ${clientPhone.value || 'Not provided'}\nVehicle: ${vehicleInfo.value || 'Not provided'}\n\nMessage: ${inquiryMessage.value || 'Requesting a quote / workshop callback.'}`
  )
  window.open(`https://wa.me/27729734018?text=${text}`, '_blank')
}

const year = computed(() => new Date().getFullYear())
</script>

<template>
  <div class="min-h-screen bg-[#0d0e11] text-neutral-100 selection:bg-red-600 selection:text-white overflow-x-hidden">

    <!-- Hero Banner with Red Ambient Flare -->
    <section class="relative isolate overflow-hidden border-b border-neutral-800 py-16 sm:py-20">
      <div class="absolute inset-0 -z-10 bg-[radial-gradient(ellipse_at_top,rgba(220,38,38,0.22),transparent_70%)]" />
      <div class="mx-auto max-w-7xl px-4 sm:px-8 lg:px-20">
        
        <div class="inline-flex items-center gap-2 px-3 py-1 mb-4 border border-neutral-700/80 bg-neutral-900/60 rounded-full text-neutral-300 text-[10px] sm:text-xs font-bold tracking-wider uppercase">
          <span class="size-1.5 rounded-full bg-red-500 animate-pulse" />
          Direct Dispatch & Workshop Comms
        </div>

        <h1 class="text-4xl sm:text-6xl font-black italic tracking-tighter uppercase text-white">
          Contact <span class="bg-gradient-to-r from-red-500 via-rose-500 to-amber-500 bg-clip-text text-transparent">La'Croc</span>
        </h1>
        <p class="mt-4 max-w-2xl text-sm sm:text-base leading-relaxed text-neutral-400">
          Reach our Ntsima workshop floor directly for emergency roadside punctures, gearbox and engine repairs, or scheduling full electronic diagnostics.
        </p>

      </div>
    </section>

    <!-- Main Comms & Dispatch Grid -->
    <section class="py-14 sm:py-20">
      <div class="mx-auto max-w-7xl px-4 sm:px-8 lg:px-20">
        <div class="grid gap-10 lg:grid-cols-12 items-start">

          <!-- Left Column: Fast Action Channels -->
          <div class="lg:col-span-5 space-y-6">

            <!-- Primary Phone Call Card -->
            <div class="border border-neutral-800 bg-[#121318] p-6 hover:border-red-600/60 transition group relative overflow-hidden shadow-xl">
              <div class="flex items-start justify-between">
                <div>
                  <span class="text-xs font-mono font-bold text-red-500">01 / DIRECT LINE</span>
                  <h3 class="mt-2 text-xl font-black uppercase text-white">Workshop Voice</h3>
                  <p class="mt-1 text-xs text-neutral-400">Speak directly with technicians on duty.</p>
                </div>
                <div class="rounded-full bg-red-950/40 p-3 border border-red-800/40 text-red-400">
                  📞
                </div>
              </div>
              <div class="mt-6">
                <a
                  href="tel:0729734018"
                  class="inline-flex w-full items-center justify-center gap-2 bg-red-600 px-5 py-3 text-xs font-black uppercase tracking-wider text-white transition hover:bg-red-500 shadow-lg shadow-red-950/60"
                >
                  <span>CALL 072 973 4018</span>
                </a>
              </div>
            </div>

            <!-- Instant WhatsApp Card -->
            <div class="border border-neutral-800 bg-[#121318] p-6 hover:border-[#25D366]/60 transition group relative overflow-hidden shadow-xl">
              <div class="flex items-start justify-between">
                <div>
                  <span class="text-xs font-mono font-bold text-[#25D366]">02 / INSTANT CHAT</span>
                  <h3 class="mt-2 text-xl font-black uppercase text-white">WhatsApp Line</h3>
                  <p class="mt-1 text-xs text-neutral-400">Fast quote requests and photo diagnosis.</p>
                </div>
                <!-- Official WhatsApp Icon Badge -->
                <div class="flex h-11 w-11 items-center justify-center rounded-full bg-[#25D366]/10 border border-[#25D366]/30 transition group-hover:bg-[#25D366]/20 group-hover:border-[#25D366]/60">
                  <svg class="h-6 w-6" viewBox="0 0 24 24" fill="none">
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M12 2C6.477 2 2 6.477 2 12C2 13.82 2.488 15.526 3.34 17L2.1 21.606L6.84 20.364C8.36 21.39 10.12 21.996 12 21.996C17.523 21.996 22 17.52 22 12C22 6.477 17.523 2 12 2Z"
                      fill="#25D366"
                    />
                    <path
                      fill-rule="evenodd"
                      clip-rule="evenodd"
                      d="M17.472 14.382C17.172 14.232 15.702 13.51 15.432 13.412C15.162 13.314 14.964 13.266 14.766 13.566C14.568 13.866 14 14.536 13.832 14.732C13.664 14.928 13.496 14.952 13.196 14.802C12.896 14.652 11.93 14.336 10.79 13.32C9.9 12.528 9.296 11.55 9.128 11.25C8.96 10.95 9.11 10.788 9.26 10.638C9.396 10.502 9.564 10.282 9.714 10.112C9.864 9.942 9.914 9.82 10.014 9.62C10.114 9.42 10.064 9.25 9.99 9.1C9.914 8.95 9.314 7.482 9.066 6.884C8.824 6.302 8.58 6.38 8.4 6.372C8.23 6.364 8.03 6.364 7.83 6.364C7.63 6.364 7.306 6.44 7.03 6.74C6.754 7.04 5.98 7.766 5.98 9.24C5.98 10.714 7.054 12.138 7.204 12.338C7.354 12.538 9.324 15.58 12.344 16.882C14.846 17.962 15.358 17.744 15.898 17.696C16.438 17.648 17.648 16.984 17.898 16.27C18.148 15.556 18.148 14.948 18.072 14.82C17.996 14.692 17.822 14.606 17.472 14.382Z"
                      fill="#FFFFFF"
                    />
                  </svg>
                </div>
              </div>
              <div class="mt-6">
                <a
                  href="https://wa.me/27729734018"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="inline-flex w-full items-center justify-center gap-2 border border-[#25D366]/80 bg-[#25D366]/10 px-5 py-3 text-xs font-black uppercase tracking-wider text-[#25D366] transition hover:bg-[#25D366] hover:text-black shadow-lg shadow-emerald-950/40"
                >
                  <span>MESSAGE VIA WHATSAPP</span>
                </a>
              </div>
            </div>

            <!-- Facility Details & Operating Hours -->
            <div class="border border-neutral-800 bg-neutral-950/60 p-6 space-y-5">
              <div>
                <span class="text-xs font-mono font-bold text-red-500 uppercase tracking-wider">Physical Address</span>
                <p class="mt-1.5 text-sm font-bold text-white">1 Sir La'Croc Avenue</p>
                <p class="text-xs text-neutral-400">Ntsima, Limpopo, 0711</p>
              </div>

              <div class="border-t border-neutral-800/80 pt-4">
                <span class="text-xs font-mono font-bold text-red-500 uppercase tracking-wider">Operational Hours</span>
                <div class="mt-2 space-y-1.5 text-xs">
                  <div class="flex justify-between text-neutral-300">
                    <span>Monday – Saturday:</span>
                    <span class="font-mono font-bold text-white">07:30 – 17:30</span>
                  </div>
                  <div class="flex justify-between text-red-400">
                    <span>Sundays & Public Holidays:</span>
                    <span class="font-mono font-bold">08:30 – 13:00</span>
                  </div>
                </div>
              </div>

              <div class="border-t border-neutral-800/80 pt-4">
                <span class="text-xs font-mono font-bold text-neutral-500 uppercase tracking-wider">Registered Entity</span>
                <p class="mt-1 text-[11px] text-neutral-400 font-mono">
                  Snoekfishmalatji Projects Pty Ltd<br />
                  Reg No: 2019/163665/07
                </p>
              </div>
            </div>

          </div>

          <!-- Right Column: Interactive Dispatch Form (WhatsApp Themed) -->
          <div class="lg:col-span-7 relative">

            <!-- Ambient WhatsApp Emerald Glow Halo -->
            <div 
              class="pointer-events-none absolute -inset-3 -z-10 rounded-2xl bg-gradient-to-r from-[#25D366]/25 via-emerald-500/20 to-teal-500/15 opacity-70 blur-3xl"
              aria-hidden="true"
            />

            <div class="border border-[#25D366]/30 bg-[#121318]/95 p-6 sm:p-8 backdrop-blur-md shadow-2xl">
              
              <div class="border-b border-neutral-800 pb-4">
                <span class="text-[10px] font-mono font-bold uppercase tracking-widest text-[#25D366]">Service Desk Dispatch</span>
                <h2 class="mt-1 text-2xl font-black italic tracking-tight text-white uppercase">Send Direct Message</h2>
                <p class="mt-1 text-xs text-neutral-400">
                  Submitting will format your query and hand off directly to our on-duty technician via WhatsApp.
                </p>
              </div>

              <form @submit.prevent="handleContactSubmit" class="mt-6 space-y-4 text-xs">
                
                <!-- Priority Selector -->
                <div>
                  <label class="block font-semibold text-neutral-300 mb-2">Service Priority:</label>
                  <div class="grid grid-cols-3 gap-2">
                    <button
                      type="button"
                      @click="inquiryType = 'quote'"
                      class="py-2 text-[10px] font-bold uppercase tracking-wider transition border rounded-none"
                      :class="inquiryType === 'quote' 
                        ? 'border-[#25D366] bg-[#25D366]/15 text-[#25D366]' 
                        : 'border-neutral-800 bg-neutral-900/60 text-neutral-400 hover:text-white'"
                    >
                      General Quote
                    </button>
                    <button
                      type="button"
                      @click="inquiryType = 'emergency'"
                      class="py-2 text-[10px] font-bold uppercase tracking-wider transition border rounded-none"
                      :class="inquiryType === 'emergency' 
                        ? 'border-red-600 bg-red-600 text-white' 
                        : 'border-neutral-800 bg-neutral-900/60 text-neutral-400 hover:text-white'"
                    >
                      Emergency
                    </button>
                    <button
                      type="button"
                      @click="inquiryType = 'general'"
                      class="py-2 text-[10px] font-bold uppercase tracking-wider transition border rounded-none"
                      :class="inquiryType === 'general' 
                        ? 'border-[#25D366] bg-[#25D366]/15 text-[#25D366]' 
                        : 'border-neutral-800 bg-neutral-900/60 text-neutral-400 hover:text-white'"
                    >
                      General Query
                    </button>
                  </div>
                </div>

                <!-- Contact Inputs -->
                <div class="grid sm:grid-cols-2 gap-4">
                  <div>
                    <label for="cName" class="block font-semibold text-neutral-300 mb-1.5">Your Name:</label>
                    <input
                      id="cName"
                      v-model="clientName"
                      type="text"
                      placeholder="e.g. John Doe"
                      class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-[#25D366] rounded-none text-xs sm:text-sm transition-colors"
                    />
                  </div>
                  <div>
                    <label for="cPhone" class="block font-semibold text-neutral-300 mb-1.5">Phone Number:</label>
                    <input
                      id="cPhone"
                      v-model="clientPhone"
                      type="tel"
                      placeholder="e.g. 072 000 0000"
                      class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-[#25D366] rounded-none text-xs sm:text-sm transition-colors"
                    />
                  </div>
                </div>

                <div>
                  <label for="cVehicle" class="block font-semibold text-neutral-300 mb-1.5">Vehicle Make & Model:</label>
                  <input
                    id="cVehicle"
                    v-model="vehicleInfo"
                    type="text"
                    placeholder="e.g. Toyota Hilux 2.8 GD-6 / VW Polo TSI"
                    class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-[#25D366] rounded-none text-xs sm:text-sm transition-colors"
                  />
                </div>

                <div>
                  <label for="cMessage" class="block font-semibold text-neutral-300 mb-1.5">Issue Description / Service Needed:</label>
                  <textarea
                    id="cMessage"
                    v-model="inquiryMessage"
                    rows="4"
                    placeholder="Describe tyre size needed, puncture location, gearbox sound, or diagnostic warnings..."
                    class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-[#25D366] rounded-none text-xs sm:text-sm resize-none transition-colors"
                  ></textarea>
                </div>

                <div class="pt-3">
                  <button
                    type="submit"
                    class="w-full inline-flex min-h-12 items-center justify-center gap-2 bg-[#25D366] hover:bg-[#20bd5a] px-6 py-3.5 text-xs font-black tracking-wider uppercase text-neutral-950 transition shadow-xl shadow-[#25D366]/20 active:translate-y-px"
                  >
                    <span>TRANSMIT VIA WHATSAPP</span>
                  </button>
                </div>

                <p class="text-[11px] text-neutral-500 text-center pt-1 font-mono">
                  Technicians reply promptly during working hours: 07:30 – 17:30.
                </p>

              </form>

            </div>

          </div>

        </div>
      </div>
    </section>

    <!-- Embedded Dark Google Map Section -->
    <section class="border-t border-neutral-800 bg-neutral-950/80 py-14 sm:py-20">
      <div class="mx-auto max-w-7xl px-4 sm:px-8 lg:px-20">
        <div class="mb-6 flex flex-col sm:flex-row items-start sm:items-center justify-between gap-4">
          <div>
            <span class="text-xs font-mono font-bold text-red-500 uppercase tracking-widest">Facility Coordinates</span>
            <h2 class="mt-1 text-2xl font-black italic uppercase text-white">Workshop Location</h2>
          </div>
          <a
            href="https://www.google.com/maps/search/?api=1&query=1+Sir+La'Croc+Avenue+Ntsima+0711"
            target="_blank"
            rel="noopener noreferrer"
            class="inline-flex items-center gap-2 border border-neutral-700 bg-neutral-900 px-4 py-2 text-xs font-bold uppercase tracking-wider text-neutral-200 hover:border-red-500 hover:text-white transition"
          >
            <span>Open in Google Maps</span>
            <span>↗</span>
          </a>
        </div>

        <div class="relative h-[360px] sm:h-[440px] w-full border border-neutral-800 bg-neutral-900 overflow-hidden">
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
          <div class="absolute bottom-4 left-4 z-10 border border-neutral-800 bg-neutral-950/90 px-3 py-2 text-xs font-medium text-neutral-300 backdrop-blur-sm pointer-events-none">
            📍 <strong class="text-white">La'Croc Workshop</strong> · 1 Sir La'Croc Ave, Ntsima
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <div class="border-t border-neutral-800 bg-neutral-900/90 px-4 py-6 text-center text-xs text-neutral-500 sm:px-8 pb-20 md:pb-6">
      © {{ year }} Snoekfishmalatji Projects Pty Ltd (Reg No.: 2019/163665/07) t/a La'Croc Tyre Health Center and Mechanical Services.
    </div>

  </div>
</template>