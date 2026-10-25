
<script setup lang="ts">
import { computed } from 'vue'

const year = computed(() => new Date().getFullYear())
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="relative isolate overflow-hidden border-b border-white/10">
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
          About La'Croc
        </p>

        <h1
          class="mt-6 max-w-4xl text-4xl font-black leading-tight tracking-tight sm:text-6xl lg:text-7xl"
        >
          A better understanding of
          <span class="text-lime-300">your vehicle.</span>
        </h1>

        <p
          class="mt-7 max-w-2xl text-base leading-7 text-stone-400 sm:text-lg sm:leading-8"
        >
          La'Croc Tyre Health Center and Mechanical Services is focused on
          automotive needs, from tyre-related concerns to mechanical
          services and vehicle diagnostics.
        </p>

        <a
          href="#our-approach"
          class="mt-9 inline-flex min-h-12 items-center justify-center gap-3 bg-lime-300 px-6 py-3 text-sm font-bold text-neutral-950 transition hover:bg-lime-200"
        >
          Get to know us
          <span aria-hidden="true">↓</span>
        </a>
      </div>
    </section>

    <!-- Introduction -->
    <section
      id="our-approach"
      class="mx-auto grid max-w-7xl gap-12 px-5 py-20 sm:px-8 sm:py-28 md:grid-cols-2 md:items-center lg:px-20"
    >
      <div>
        <p
          class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
        >
          Who we are
        </p>

        <h2
          class="mt-5 text-3xl font-bold leading-tight tracking-tight sm:text-4xl"
        >
          Every vehicle has a story. Let's understand yours.
        </h2>

        <div class="mt-6 space-y-5 text-sm leading-7 text-stone-400 sm:text-base">
          <p>
            Vehicle problems can be frustrating, especially when you're
            unsure where to begin. Finding the right place to discuss your
            concerns is an important first step.
          </p>

          <p>
            At La'Croc Tyre Health Center and Mechanical Services, you can
            get in touch to discuss your vehicle's needs and enquire about
            the services available for your situation.
          </p>

          <p>
            Whether you have a tyre-related concern, a mechanical issue,
            or questions about vehicle diagnostics, our aim is to help you
            identify the next steps available to you.
          </p>
        </div>
      </div>

      <!-- Replace with an approved photo of the actual workshop -->
      <div class="relative">
        <div
          class="absolute -inset-3 -z-10 border border-lime-300/20"
        />

        <img
          src="https://images.unsplash.com/photo-1486262715619-67b85e0b08d3?auto=format&fit=crop&w=1200&q=85"
          alt="Automotive workshop environment"
          loading="lazy"
          class="aspect-[4/5] w-full object-cover sm:aspect-[5/4] md:aspect-[4/5]"
        />

        <div
          class="absolute inset-x-0 bottom-0 bg-gradient-to-t from-black/90 to-transparent p-6 pt-20 sm:p-8 sm:pt-24"
        >
          <p
            class="text-xs font-semibold uppercase tracking-[0.2em] text-lime-300"
          >
            La'Croc Motor Services
          </p>

          <p class="mt-2 text-xl font-bold text-white sm:text-2xl">
            Your vehicle. Our attention.
          </p>
        </div>
      </div>
    </section>

    <!-- Our approach -->
    <section class="border-y border-white/10 bg-[#171917] py-20 sm:py-28">
      <div class="mx-auto max-w-7xl px-5 sm:px-8 lg:px-20">
        <div class="max-w-2xl">
          <p
            class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
          >
            Our approach
          </p>

          <h2 class="mt-4 text-3xl font-bold tracking-tight sm:text-4xl">
            Start with the problem. Work towards a solution.
          </h2>

          <p class="mt-5 text-sm leading-7 text-stone-400 sm:text-base">
            Understanding what your vehicle needs begins with a clear
            conversation about the issue and the available options.
          </p>
        </div>

        <div class="mt-12 grid gap-5 md:grid-cols-3">
          <article
            class="border border-white/10 bg-[#101110] p-6 sm:p-8"
          >
            <span class="text-sm font-bold text-lime-300">01</span>

            <h3 class="mt-6 text-xl font-bold">
              Listen and understand
            </h3>

            <p class="mt-4 text-sm leading-7 text-stone-400">
              Tell us about your vehicle, the symptoms you're experiencing,
              or the service you're looking for.
            </p>
          </article>

          <article
            class="border border-white/10 bg-[#101110] p-6 sm:p-8"
          >
            <span class="text-sm font-bold text-lime-300">02</span>

            <h3 class="mt-6 text-xl font-bold">
              Explore your options
            </h3>

            <p class="mt-4 text-sm leading-7 text-stone-400">
              Discuss your requirements with the team and confirm which
              services are available for your vehicle.
            </p>
          </article>

          <article
            class="border border-white/10 bg-[#101110] p-6 sm:p-8"
          >
            <span class="text-sm font-bold text-lime-300">03</span>

            <h3 class="mt-6 text-xl font-bold">
              Plan the next step
            </h3>

            <p class="mt-4 text-sm leading-7 text-stone-400">
              Establish the next steps with the workshop before proceeding
              with any service or repair.
            </p>
          </article>
        </div>
      </div>
    </section>

    <!-- Service coverage -->
    <section class="mx-auto max-w-7xl px-5 py-20 sm:px-8 sm:py-28 lg:px-20">
      <div class="grid gap-8 md:grid-cols-2 md:items-center">
        <div>
          <p
            class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
          >
            What we work with
          </p>

          <h2 class="mt-4 text-3xl font-bold tracking-tight sm:text-4xl">
            Automotive needs, all in one conversation.
          </h2>

          <p class="mt-5 text-sm leading-7 text-stone-400 sm:text-base">
            La'Croc caters to enquiries involving different vehicles and
            vehicle systems. Contact the team to discuss your particular
            vehicle and confirm the assistance available.
          </p>

          <RouterLink
            to="/services"
            class="mt-8 inline-flex items-center gap-3 text-sm font-bold text-lime-300 transition hover:text-lime-200"
          >
            Explore our services
            <span aria-hidden="true">→</span>
          </RouterLink>
        </div>

        <div class="border border-white/10 bg-[#171917] p-6 sm:p-8">
          <div class="flex items-center gap-4 border-b border-white/10 py-5 first:pt-0">
            <span
              class="grid size-10 shrink-0 place-items-center border border-lime-300/20 text-lg text-lime-300"
              aria-hidden="true"
            >
              ◉
            </span>

            <div>
              <h3 class="font-bold">Tyre-related needs</h3>
              <p class="mt-1 text-sm leading-6 text-stone-400">
                Enquiries about tyre health and maintenance.
              </p>
            </div>
          </div>

          <div class="flex items-center gap-4 border-b border-white/10 py-5">
            <span
              class="grid size-10 shrink-0 place-items-center border border-lime-300/20 text-lg text-lime-300"
              aria-hidden="true"
            >
              ⚙
            </span>

            <div>
              <h3 class="font-bold">Mechanical services</h3>
              <p class="mt-1 text-sm leading-6 text-stone-400">
                Enquiries about mechanical concerns and repairs.
              </p>
            </div>
          </div>

          <div class="flex items-center gap-4 py-5 pb-0">
            <span
              class="grid size-10 shrink-0 place-items-center border border-lime-300/20 text-lg text-lime-300"
              aria-hidden="true"
            >
              ⌁
            </span>

            <div>
              <h3 class="font-bold">Vehicle diagnostics</h3>
              <p class="mt-1 text-sm leading-6 text-stone-400">
                Enquiries involving vehicle systems and diagnostics.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact CTA -->
    <section
      class="mx-auto max-w-7xl px-5 pb-20 sm:px-8 sm:pb-28 lg:px-20"
    >
      <div
        class="relative isolate overflow-hidden border border-lime-300/30 bg-[#171917] p-7 sm:p-12 lg:p-16"
      >
        <div
          class="absolute -right-16 -top-16 -z-10 size-64 rounded-full border border-lime-300/10"
        />

        <div class="relative max-w-2xl">
          <p
            class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
          >
            Get in touch
          </p>

          <h2 class="mt-5 text-3xl font-black tracking-tight sm:text-5xl">
            Let's talk about your vehicle.
          </h2>

          <p class="mt-5 text-sm leading-7 text-stone-400 sm:text-base">
            Have a question or need assistance? Contact the team to discuss
            your vehicle and enquire about available services.
          </p>

          <RouterLink
            to="/services"
            class="mt-8 inline-flex min-h-12 items-center justify-center gap-3 bg-lime-300 px-6 py-3 text-sm font-bold text-neutral-950 transition hover:bg-lime-200"
          >
            View our services
            <span aria-hidden="true">↗</span>
          </RouterLink>
        </div>
      </div>
    </section>

    <!-- Page footer -->
    <div
      class="border-t border-white/10 px-5 py-5 text-center text-xs text-stone-500 sm:px-8"
    >
      © {{ year }} La'Croc Tyre Health Center and Mechanical Services.
      All rights reserved.
    </div>
  </div>
</template>

