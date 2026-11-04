<script setup lang="ts">
const stats = [
  { value: '100%', label: 'Registered Entity', detail: 'Reg: 2019/163665/07' },
  { value: '0711', label: 'Local Facility', detail: '1 Sir La\'Croc Ave, Ntsima' },
  { value: 'Mon-Sun', label: 'Operational Coverage', detail: 'Open 7 Days a Week' },
  { value: 'OBD-II', label: 'Modern Diagnostics', detail: 'Multi-make scanning' },
]

const values = [
  {
    num: '01',
    title: 'Precision Tyre Care',
    desc: 'From patch-plug puncture sealing to balanced tyre fitment, every wheel is inspected for true road safety and tread longevity.'
  },
  {
    num: '02',
    title: 'Transparent Mechanicals',
    desc: 'No ghost faults or inflated bills. Direct assessment of gearboxes, cooling systems, brakes, and drivetrain components.'
  },
  {
    num: '03',
    title: 'Rapid Turnaround',
    desc: 'Positioned strategically in Ntsima to keep commercial bakkies, fleets, and daily commuters on the road without prolonged workshop downtime.'
  }
]
</script>

<template>
  <div class="min-h-screen bg-[#0d0e11] text-neutral-100 selection:bg-red-600 selection:text-white">

    <!-- Header Banner -->
    <section class="relative isolate overflow-hidden border-b border-neutral-800 py-16 sm:py-24">
      <div class="absolute inset-0 -z-10 bg-[radial-gradient(ellipse_at_top,rgba(220,38,38,0.18),transparent_65%)]" />
      
      <div class="mx-auto max-w-7xl px-4 sm:px-8 lg:px-20">
        <div class="inline-flex items-center gap-2 px-3 py-1 mb-4 border border-neutral-700/80 bg-neutral-900/60 rounded-full text-neutral-300 text-[10px] sm:text-xs font-bold tracking-wider uppercase">
          <span class="size-1.5 rounded-full bg-red-500" />
          About La'Croc
        </div>

        <h1 class="text-4xl sm:text-6xl font-black italic tracking-tighter uppercase text-white">
          Engineered to Keep You <span class="bg-gradient-to-r from-red-500 to-amber-500 bg-clip-text text-transparent">Moving</span>
        </h1>
        <p class="mt-4 max-w-2xl text-sm sm:text-base leading-relaxed text-neutral-400">
          La'Croc Tyre Health Center is a premier independent automotive workshop in Ntsima, operated under Snoekfishmalatji Projects Pty Ltd. Built on industrial-grade standards, honest diagnostics, and rapid turnaround.
        </p>

        <!-- Metric Grid -->
        <div class="mt-12 grid grid-cols-2 gap-4 lg:grid-cols-4">
          <div 
            v-for="s in stats" 
            :key="s.label"
            class="border border-neutral-800 bg-[#121318]/90 p-5 backdrop-blur-sm hover:border-red-600/40 transition"
          >
            <div class="text-2xl sm:text-3xl font-black font-mono text-red-500">{{ s.value }}</div>
            <div class="mt-1 text-xs font-bold uppercase tracking-wider text-white">{{ s.label }}</div>
            <div class="mt-0.5 text-[11px] text-neutral-500 font-mono">{{ s.detail }}</div>
          </div>
        </div>
      </div>
    </section>

    <!-- Operational Philosophy -->
    <section class="py-16 sm:py-24">
      <div class="mx-auto max-w-7xl px-4 sm:px-8 lg:px-20">
        <div class="mb-10">
          <span class="text-xs font-mono font-bold uppercase tracking-widest text-red-500">Standards & Protocol</span>
          <h2 class="mt-2 text-2xl sm:text-3xl font-black italic uppercase text-white">How We Operate</h2>
        </div>

        <div class="grid gap-6 md:grid-cols-3">
          <div 
            v-for="val in values" 
            :key="val.num"
            class="border border-neutral-800 bg-[#121318] p-6 hover:border-red-600/60 transition group flex flex-col justify-between"
          >
            <div>
              <span class="text-xs font-mono font-bold text-red-500">{{ val.num }} /</span>
              <h3 class="mt-3 text-lg font-black uppercase text-white group-hover:text-red-400 transition">
                {{ val.title }}
              </h3>
              <p class="mt-2 text-xs leading-relaxed text-neutral-400">
                {{ val.desc }}
              </p>
            </div>
            <div class="mt-6 pt-4 border-t border-neutral-800/80 flex items-center justify-between text-[11px] font-mono text-neutral-500">
              <span>WORKSHOP STANDARD</span>
              <span class="text-red-500 font-bold">READY</span>
            </div>
          </div>
        </div>

        <!-- Corporate Registration Card -->
        <div class="mt-12 border border-neutral-800 bg-neutral-900/60 p-6 sm:p-8 flex flex-col sm:flex-row items-start sm:items-center justify-between gap-6">
          <div>
            <span class="text-[10px] font-mono font-bold uppercase tracking-wider text-neutral-400">Entity Details</span>
            <h4 class="text-lg font-bold text-white mt-1">Snoekfishmalatji Projects Pty Ltd</h4>
            <p class="text-xs text-neutral-400 mt-0.5 font-mono">Company Registration: 2019/163665/07</p>
          </div>

          <a 
            href="tel:0729734018"
            class="inline-flex items-center justify-center bg-red-600 px-6 py-3 text-xs font-black uppercase tracking-wider text-white hover:bg-red-500 transition shadow-lg shadow-red-950/40"
          >
            Contact Direct
          </a>
        </div>
      </div>
    </section>

  </div>
</template>