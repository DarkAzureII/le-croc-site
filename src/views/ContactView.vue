
<script setup lang="ts">
import { computed, ref } from 'vue'

const year = computed(() => new Date().getFullYear())

const form = ref({
  name: '',
  phone: '',
  email: '',
  service: '',
  message: '',
})

const submitted = ref(false)

function handleSubmit() {
  submitted.value = true
}
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
          Contact us
        </p>

        <h1
          class="mt-6 max-w-4xl text-4xl font-black leading-tight tracking-tight sm:text-6xl lg:text-7xl"
        >
          Let's talk about
          <span class="text-lime-300">your vehicle.</span>
        </h1>

        <p
          class="mt-7 max-w-2xl text-base leading-7 text-stone-400 sm:text-lg sm:leading-8"
        >
          Have a question about tyres, mechanical services, or vehicle
          diagnostics? Tell us what you need and we'll help you take the
          next step.
        </p>
      </div>
    </section>

    <!-- Contact content -->
    <section
      class="mx-auto grid max-w-7xl gap-12 px-5 py-16 sm:px-8 sm:py-20 lg:grid-cols-[0.8fr_1.2fr] lg:gap-20 lg:px-20"
    >
      <!-- Contact information -->
      <aside>
        <p
          class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
        >
          Get in touch
        </p>

        <h2 class="mt-4 text-3xl font-bold tracking-tight">
          We're ready to listen.
        </h2>

        <p class="mt-5 text-sm leading-7 text-stone-400">
          Every vehicle concern is different. Share a few details about
          your enquiry so the team can understand what assistance you're
          looking for.
        </p>

        <div class="mt-10 space-y-6">
          <div class="flex gap-4 border-t border-white/10 pt-6">
            <span
              class="grid size-11 shrink-0 place-items-center border border-lime-300/20 text-lg text-lime-300"
              aria-hidden="true"
            >
              ↗
            </span>

            <div>
              <h3 class="font-bold">General enquiries</h3>
              <p class="mt-2 text-sm leading-6 text-stone-400">
                Ask about available services and discuss your vehicle's
                needs.
              </p>
            </div>
          </div>

          <div class="flex gap-4 border-t border-white/10 pt-6">
            <span
              class="grid size-11 shrink-0 place-items-center border border-lime-300/20 text-lg text-lime-300"
              aria-hidden="true"
            >
              ⚙
            </span>

            <div>
              <h3 class="font-bold">Service enquiries</h3>
              <p class="mt-2 text-sm leading-6 text-stone-400">
                Tell us whether your enquiry concerns tyres, mechanical
                services, or diagnostics.
              </p>
            </div>
          </div>

          <div class="flex gap-4 border-t border-white/10 pt-6">
            <span
              class="grid size-11 shrink-0 place-items-center border border-lime-300/20 text-lg text-lime-300"
              aria-hidden="true"
            >
              ◷
            </span>

            <div>
              <h3 class="font-bold">Operating hours</h3>
              <p class="mt-2 text-sm leading-6 text-stone-400">
                Contact the workshop to confirm opening hours and
                availability.
              </p>
            </div>
          </div>
        </div>

        <div class="mt-10 border border-white/10 bg-[#171917] p-6">
          <p class="text-sm font-bold text-lime-300">
            La'Croc Tyre Health Center
          </p>

          <p class="mt-2 text-sm leading-6 text-stone-400">
            Tyre Health Center and Mechanical Services
          </p>
        </div>
      </aside>

      <!-- Enquiry form -->
      <div class="border border-white/10 bg-[#171917] p-6 sm:p-10">
        <div v-if="!submitted">
          <p
            class="text-xs font-bold uppercase tracking-[0.22em] text-lime-300"
          >
            Send an enquiry
          </p>

          <h2 class="mt-4 text-2xl font-bold tracking-tight sm:text-3xl">
            How can we help?
          </h2>

          <p class="mt-3 text-sm leading-6 text-stone-400">
            Complete the fields below. All fields marked with * are
            required.
          </p>

          <form
            class="mt-8 space-y-6"
            @submit.prevent="handleSubmit"
          >
            <div>
              <label
                for="name"
                class="mb-2 block text-sm font-semibold"
              >
                Full name *
              </label>

              <input
                id="name"
                v-model.trim="form.name"
                name="name"
                type="text"
                autocomplete="name"
                required
                placeholder="Your name"
                class="min-h-12 w-full border border-white/15 bg-[#101110] px-4 py-3 text-sm text-stone-100 outline-none transition placeholder:text-stone-600 focus:border-lime-300"
              />
            </div>

            <div class="grid gap-6 sm:grid-cols-2">
              <div>
                <label
                  for="phone"
                  class="mb-2 block text-sm font-semibold"
                >
                  Phone number *
                </label>

                <input
                  id="phone"
                  v-model.trim="form.phone"
                  name="phone"
                  type="tel"
                  autocomplete="tel"
                  required
                  placeholder="Your phone number"
                  class="min-h-12 w-full border border-white/15 bg-[#101110] px-4 py-3 text-sm outline-none transition placeholder:text-stone-600 focus:border-lime-300"
                />
              </div>

              <div>
                <label
                  for="email"
                  class="mb-2 block text-sm font-semibold"
                >
                  Email address
                </label>

                <input
                  id="email"
                  v-model.trim="form.email"
                  name="email"
                  type="email"
                  autocomplete="email"
                  placeholder="you@example.com"
                  class="min-h-12 w-full border border-white/15 bg-[#101110] px-4 py-3 text-sm outline-none transition placeholder:text-stone-600 focus:border-lime-300"
                />
              </div>
            </div>

            <div>
              <label
                for="service"
                class="mb-2 block text-sm font-semibold"
              >
                What do you need help with? *
              </label>

              <select
                id="service"
                v-model="form.service"
                name="service"
                required
                class="min-h-12 w-full border border-white/15 bg-[#101110] px-4 py-3 text-sm text-stone-300 outline-none transition focus:border-lime-300"
              >
                <option disabled value="">Select a service</option>
                <option value="Tyre services">Tyre services</option>
                <option value="Mechanical services">
                  Mechanical services
                </option>
                <option value="Vehicle diagnostics">
                  Vehicle diagnostics
                </option>
                <option value="General enquiry">General enquiry</option>
                <option value="Other">Other</option>
              </select>
            </div>

            <div>
              <label
                for="message"
                class="mb-2 block text-sm font-semibold"
              >
                Tell us more *
              </label>

              <textarea
                id="message"
                v-model.trim="form.message"
                name="message"
                required
                rows="5"
                placeholder="Briefly describe your enquiry..."
                class="w-full resize-y border border-white/15 bg-[#101110] px-4 py-3 text-sm leading-6 outline-none transition placeholder:text-stone-600 focus:border-lime-300"
              />
            </div>

            <button
              type="submit"
              class="inline-flex min-h-12 w-full items-center justify-center gap-3 bg-lime-300 px-6 py-3 text-sm font-bold text-neutral-950 transition hover:bg-lime-200"
            >
              Submit enquiry
              <span aria-hidden="true">↗</span>
            </button>

            <p class="text-xs leading-5 text-stone-500">
              This form is currently a frontend prototype. Messages
              are not sent or stored yet.
            </p>
          </form>
        </div>

        <!-- Prototype confirmation -->
        <div v-else class="py-10 text-center">
          <span
            class="mx-auto grid size-14 place-items-center border border-lime-300/30 text-2xl text-lime-300"
            aria-hidden="true"
          >
            ✓
          </span>

          <h2 class="mt-6 text-2xl font-bold">
            Form prototype tested
          </h2>

          <p class="mx-auto mt-4 max-w-md text-sm leading-7 text-stone-400">
            The form validation worked, but your enquiry has not been
            sent to La'Croc. A submission service must be connected
            before this form can receive real enquiries.
          </p>

          <button
            type="button"
            class="mt-8 border border-white/15 px-5 py-3 text-sm font-semibold transition hover:border-lime-300 hover:text-lime-300"
            @click="submitted = false"
          >
            Back to form
          </button>
        </div>
      </div>
    </section>

    <!-- Bottom CTA -->
    <section class="border-t border-white/10 bg-[#171917]">
      <div
        class="mx-auto flex max-w-7xl flex-col gap-5 px-5 py-10 sm:px-8 md:flex-row md:items-center md:justify-between lg:px-20"
      >
        <div>
          <h2 class="text-xl font-bold">
            Want to explore our services first?
          </h2>

          <p class="mt-2 text-sm text-stone-400">
            Learn more about the automotive assistance you can enquire
            about.
          </p>
        </div>

        <RouterLink
          to="/services"
          class="inline-flex min-h-12 items-center justify-center gap-3 border border-white/15 px-5 py-3 text-sm font-semibold transition hover:border-lime-300 hover:text-lime-300"
        >
          View services
          <span aria-hidden="true">→</span>
        </RouterLink>
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
