
<script setup lang="ts">
import { computed } from 'vue'

interface Service {
  number: string
  title: string
  description: string
  details: string[]
  icon: string
}

const services: Service[] = [
  {
    number: '01',
    title: 'Tyre Services',
    description:
      'Your tyres play an important role in your vehicle’s safety, stability, and performance. Contact our team to discuss your tyre-related needs.',
    details: [
      'Tyre condition enquiries',
      'Tyre maintenance enquiries',
      'General tyre assistance',
    ],
    icon: '◉',
  },
  {
    number: '02',
    title: 'Mechanical Services',
    description:
      'Experiencing a vehicle problem? Get in touch with our team to discuss your concerns and find out how we can assist.',
    details: [
      'Mechanical problem enquiries',
      'Vehicle maintenance enquiries',
      'Repair service enquiries',
    ],
    icon: '⚙',
  },
  {
    number: '03',
    title: 'Vehicle Diagnostics',
    description:
      'Understanding a vehicle problem starts with identifying what may be causing it. Contact us to enquire about diagnostic services for your vehicle.',
    details: [
      'Vehicle diagnostic enquiries',
      'Vehicle system problem enquiries',
      'Assistance identifying vehicle issues',
    ],
    icon: '⌁',
  },
]

const year = computed(() => new Date().getFullYear())
</script>

<template>
  <div>
    <!-- Hero -->
    <section
      class="relative isolate overflow-hidden border-b border-white/10"
    >
      <div
        class="absolute inset-0 -z-10 bg-[radial-gradient(ellipse_at_75%_35%,rgba(163,230,53,0.12),transparent_55%)]"
      />

      <div
        class="mx-auto max-w-7xl px-5 py-20 sm:px-8 sm:py-28 lg:px-20 lg:py-32"
      >
        <p
          class="flex items-center gap-3 text-xs font-bold uppercase tracking-[0.24em] text-lime-300"
        >
          <span class="h-px w-8 bg-lime-300" />
          What we do
        </p>

        <h1
          class="mt-6 max-w-4xl text-4xl font-black leading-tight tracking-tight sm:text-6xl lg:text-7xl"
        >
          Keeping your vehicle
          <span class="text-lime-300">moving.</span>
        </h1>

        <p
          class="mt-7 max-w-2xl text-base leading-7 text-stone-400 sm:text-lg sm:leading-8"
        >
          From tyre-related concerns to mechanical issues and vehicle
          diagnostics, get in touch with our team to discuss your vehicle's
          needs and the services available to you.
        </p>

        <div class="mt-9 flex flex-col gap-3 sm:flex-row">
          <a
            href="#service-list"
            class="inline-flex min-h-12 items-center justify-center bg-lime-300 px-6 py-3 text-sm font-bold text-neutral-950 transition hover:bg-lime-200"
          >
            Explore our services
            <span class="ml-3" aria-hidden="true">↓</span>
          </a>

          <a
            href="#contact"
            class="inline-flex min-h-12 items-center justify-center border border-white/15 px-6 py-3 text-sm font-semibold transition hover:border-lime-300 hover:text-lime-300"
          >
            Make an enquiry
            <span class="ml-3" aria-hidden="true">↗</span>
          </a>
        </div>
      </div>
    </section>

    <!-- Introduction -->
    <section
      class="mx-auto grid max-w-7xl gap-8 px-5 py-16 sm:px-8 sm:py-20 md:grid-cols-2 md:items-end lg:px-20"
    >
      <div>
        <p
          class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
        >
          Automotive care
        </p>

        <h2
          class="mt-5 max-w-xl text-3xl font-bold leading-tight tracking-tight sm:text-4xl"
        >
          Every vehicle deserves the right attention.
        </h2>
      </div>

      <p class="max-w-xl text-sm leading-7 text-stone-400 sm:text-base">
        Whether you have a concern about your tyres, need help understanding
        a mechanical problem, or want to enquire about vehicle diagnostics,
        start by telling us what your vehicle needs.
      </p>
    </section>

    <!-- Services -->
    <section
      id="service-list"
      class="border-y border-white/10 bg-[#171917] py-20 sm:py-28"
    >
      <div class="mx-auto max-w-7xl px-5 sm:px-8 lg:px-20">
        <div
          class="flex flex-col gap-5 sm:flex-row sm:items-end sm:justify-between"
        >
          <div>
            <p
              class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
            >
              How we can help
            </p>

            <h2 class="mt-4 text-3xl font-bold tracking-tight sm:text-4xl">
              Our services
            </h2>
          </div>

          <p class="max-w-md text-sm leading-6 text-stone-400">
            Contact us to confirm service availability and discuss the
            requirements of your vehicle.
          </p>
        </div>

        <div class="mt-12 grid gap-5 md:grid-cols-2 lg:grid-cols-3">
          <article
            v-for="service in services"
            :key="service.number"
            class="group flex flex-col border border-white/10 bg-[#101110] p-6 transition duration-300 hover:-translate-y-1 hover:border-lime-300/50 sm:p-8"
          >
            <div class="flex items-center justify-between">
              <span
                class="grid size-12 place-items-center border border-lime-300/20 text-2xl text-lime-300"
                aria-hidden="true"
              >
                {{ service.icon }}
              </span>

              <span class="text-sm font-bold tracking-widest text-stone-600">
                {{ service.number }}
              </span>
            </div>

            <h3 class="mt-8 text-xl font-bold tracking-tight">
              {{ service.title }}
            </h3>

            <p class="mt-4 text-sm leading-7 text-stone-400">
              {{ service.description }}
            </p>

            <ul class="mt-6 space-y-3 border-t border-white/10 pt-6">
              <li
                v-for="detail in service.details"
                :key="detail"
                class="flex items-start gap-3 text-sm leading-6 text-stone-300"
              >
                <span class="mt-0.5 text-lime-300" aria-hidden="true">
                  +
                </span>
                <span>{{ detail }}</span>
              </li>
            </ul>

            <a
              href="#contact"
              class="mt-8 inline-flex items-center gap-2 text-sm font-semibold text-lime-300 transition group-hover:gap-3 hover:text-lime-200"
            >
              Enquire about this service
              <span aria-hidden="true">→</span>
            </a>
          </article>
        </div>
      </div>
    </section>

    <!-- Process -->
    <section
      class="mx-auto max-w-7xl px-5 py-20 sm:px-8 sm:py-28 lg:px-20"
    >
      <p
        class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
      >
        Getting started
      </p>

      <h2 class="mt-4 max-w-2xl text-3xl font-bold tracking-tight sm:text-4xl">
        Getting help starts with a conversation.
      </h2>

      <div class="mt-12 grid gap-8 sm:grid-cols-3">
        <div class="border-t border-white/15 pt-6">
          <span class="text-sm font-bold text-lime-300">01 / ENQUIRE</span>
          <h3 class="mt-4 text-lg font-bold">Tell us what's happening</h3>
          <p class="mt-3 text-sm leading-7 text-stone-400">
            Describe the issue you're experiencing or the service you're
            looking for.
          </p>
        </div>

        <div class="border-t border-white/15 pt-6">
          <span class="text-sm font-bold text-lime-300">02 / DISCUSS</span>
          <h3 class="mt-4 text-lg font-bold">Discuss your needs</h3>
          <p class="mt-3 text-sm leading-7 text-stone-400">
            Speak with the team about your vehicle and the available
            service options.
          </p>
        </div>

        <div class="border-t border-white/15 pt-6">
          <span class="text-sm font-bold text-lime-300">03 / NEXT STEPS</span>
          <h3 class="mt-4 text-lg font-bold">Plan your next step</h3>
          <p class="mt-3 text-sm leading-7 text-stone-400">
            Confirm the appropriate next steps with the workshop before
            arranging any work.
          </p>
        </div>
      </div>
    </section>

    <!-- Contact CTA -->
    <section
      id="contact"
      class="mx-auto max-w-7xl px-5 pb-20 sm:px-8 sm:pb-28 lg:px-20"
    >
      <div
        class="relative isolate overflow-hidden border border-lime-300/30 bg-[#171917] p-7 sm:p-12 lg:p-16"
      >
        <div
          class="absolute -right-16 -top-16 -z-10 size-64 rounded-full border border-lime-300/10"
        />
        <div
          class="absolute -right-8 -top-8 -z-10 size-48 rounded-full border border-lime-300/10"
        />

        <div class="max-w-2xl">
          <p
            class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
          >
            Let's talk
          </p>

          <h2
            class="mt-5 text-3xl font-black tracking-tight sm:text-5xl"
          >
            Your vehicle. Our attention.
          </h2>

          <p class="mt-5 text-sm leading-7 text-stone-400 sm:text-base">
            Have a question about our services? Get in touch with the team
            to discuss your vehicle and confirm how we can help.
          </p>

          <p class="mt-6 text-sm text-stone-500">
            Contact details will be added once confirmed by the business.
          </p>

          <a
            href="/#contact"
            class="mt-8 inline-flex min-h-12 items-center justify-center gap-3 bg-lime-300 px-6 py-3 text-sm font-bold text-neutral-950 transition hover:bg-lime-200"
          >
            Contact the team
            <span aria-hidden="true">↗</span>
          </a>
        </div>
      </div>
    </section>

    <!-- Page footer -->
    <div
      class="border-t border-white/10 px-5 py-5 text-center text-xs text-stone-500 sm:px-8"
    >
      © {{ year }} Le Croc Motor Services. All rights reserved.
    </div>
  </div>
</template>
