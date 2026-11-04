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
            <div class="border border-neutral-800 bg-[#121318] p-6 hover:border-emerald-500/60 transition group relative overflow-hidden shadow-xl">
              <div class="flex items-start justify-between">
                <div>
                  <span class="text-xs font-mono font-bold text-emerald-400">02 / INSTANT CHAT</span>
                  <h3 class="mt-2 text-xl font-black uppercase text-white">WhatsApp Line</h3>
                  <p class="mt-1 text-xs text-neutral-400">Fast quote requests and photo diagnosis.</p>
                </div>
                <div class="rounded-full bg-emerald-950/40 p-3 border border-emerald-800/40 text-emerald-400">
                  💬
                </div>
              </div>
              <div class="mt-6">
                <a
                  href="https://wa.me/27729734018"
                  target="_blank"
                  rel="noopener noreferrer"
                  class="inline-flex w-full items-center justify-center gap-2 border border-emerald-600/80 bg-emerald-950/30 px-5 py-3 text-xs font-black uppercase tracking-wider text-emerald-300 transition hover:bg-emerald-600 hover:text-white"
                >
                  <span>MESSAGE VIA WHATSAPP</span>
                  <span>↗</span>
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
                  Reg No: 2019/16366/07
                </p>
              </div>
            </div>

          </div>

          <!-- Right Column: Interactive Dispatch Form -->
          <div class="lg:col-span-7 relative">

            <!-- Ambient Split-Glow Halo -->
            <div 
              class="pointer-events-none absolute -inset-3 -z-10 rounded-2xl bg-gradient-to-r from-red-600/30 via-rose-500/15 to-amber-400/25 opacity-70 blur-3xl"
              aria-hidden="true"
            />

            <div class="border border-neutral-800 bg-[#121318]/95 p-6 sm:p-8 backdrop-blur-md shadow-2xl">
              
              <div class="border-b border-neutral-800 pb-4">
                <span class="text-[10px] font-mono font-bold uppercase tracking-widest text-red-500">Service Desk Dispatch</span>
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
                        ? 'border-red-500 bg-red-950/40 text-red-400' 
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
                      🚨 Emergency
                    </button>
                    <button
                      type="button"
                      @click="inquiryType = 'general'"
                      class="py-2 text-[10px] font-bold uppercase tracking-wider transition border rounded-none"
                      :class="inquiryType === 'general' 
                        ? 'border-red-500 bg-red-950/40 text-red-400' 
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
                      class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-red-500 rounded-none text-xs sm:text-sm"
                    />
                  </div>
                  <div>
                    <label for="cPhone" class="block font-semibold text-neutral-300 mb-1.5">Phone Number:</label>
                    <input
                      id="cPhone"
                      v-model="clientPhone"
                      type="tel"
                      placeholder="e.g. 072 000 0000"
                      class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-red-500 rounded-none text-xs sm:text-sm"
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
                    class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-red-500 rounded-none text-xs sm:text-sm"
                  />
                </div>

                <div>
                  <label for="cMessage" class="block font-semibold text-neutral-300 mb-1.5">Issue Description / Service Needed:</label>
                  <textarea
                    id="cMessage"
                    v-model="inquiryMessage"
                    rows="4"
                    placeholder="Describe tyre size needed, puncture location, gearbox sound, or diagnostic warnings..."
                    class="w-full border border-neutral-700/80 bg-neutral-900/90 px-3.5 py-2.5 text-neutral-200 outline-none focus:border-red-500 rounded-none text-xs sm:text-sm resize-none"
                  ></textarea>
                </div>

                <div class="pt-3">
                  <button
                    type="submit"
                    class="w-full inline-flex min-h-12 items-center justify-center gap-2 bg-red-600 px-6 py-3.5 text-xs font-black tracking-wider uppercase text-white transition hover:bg-red-500 shadow-xl shadow-red-950/60"
                  >
                    <span>TRANSMIT VIA WHATSAPP DISPATCH</span>
                    <span aria-hidden="true">↗</span>
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