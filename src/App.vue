<script setup>
import BrandLogo from '@/components/BrandLogo.vue'

const EMAIL = 'ray@mecha.my'
const MAILTO = `mailto:${EMAIL}?subject=%5BMechaCraft%5D%20I%20have%20an%20enquiry`

const services = [
  {
    title: 'SaaS Development',
    body: 'Multi-tenant systems for performance and scalability.',
    items: ['Subscription & billing', 'License & plan controls', 'Multi-tenant architecture', 'Payment integrations', 'Production infrastructure'],
  },
  {
    title: 'AI & Automation',
    body: 'AI integrated into workflows as productivity multipliers.',
    items: ['Workflow automation', 'LLM integrations', 'Data pipelines', 'Process automation', 'AI-native features'],
  },
  {
    title: 'Retail & Property',
    body: 'Systems that power real-world operations.',
    items: ['POS integrations', 'Loyalty systems', 'Retail CRM', 'Property management', 'Operations workflows'],
  },
]

// Products without a live site leave `url` unset, render unlinked and go last.
const products = [
  {
    name: 'RewardLah',
    category: 'Loyalty & retail CRM',
    body: 'Loyalty points and CRM for SMEs. Retain customers and drive repeat purchases through intelligent reward systems and insights.',
    url: 'https://rewardlah.com',
    domain: 'rewardlah.com',
  },
  {
    name: 'Rakan Boss',
    category: 'HR & payroll',
    body: 'Payroll for Malaysian businesses. Calculates EPF, SOCSO, EIS and PCB, routes every run through maker-checker approvals, and produces bank-ready Maybank2E files.',
    url: 'https://rakanboss.com',
    domain: 'rakanboss.com',
  },
  {
    name: 'housemonkey',
    category: 'Property management',
    body: 'Rental and property management for landlords, investors, and agencies. Tools for tenant screening, rent collection, and maintenance.',
  },
]

const year = new Date().getFullYear()
</script>

<template>
  <div class="min-h-screen bg-paper text-ink">
    <header class="sticky top-0 z-10 border-b border-rule bg-paper/90 backdrop-blur">
      <div class="shell flex h-16 items-center justify-between">
        <a href="#top" aria-label="MechaCraft, back to top">
          <BrandLogo class="h-5 w-auto" />
        </a>
        <nav class="flex items-center gap-6 text-sm text-ink-2 sm:gap-8">
          <a href="#services" class="nav hidden sm:inline">Services</a>
          <a href="#products" class="nav hidden sm:inline">Products</a>
          <a href="#contact" class="btn btn-sm cut">Contact</a>
        </nav>
      </div>
    </header>

    <main id="top">
      <!-- Hero -->
      <section class="shell grid items-end gap-12 pt-20 pb-24 md:grid-cols-12 md:pt-32 md:pb-32">
        <div class="md:col-span-8">
          <p class="eyebrow">MechaCraft · Kuala Lumpur</p>
          <h1 class="display mt-6"><span class="md:block">Engineered for scale.</span> <span class="md:block">Built for revenue.</span></h1>
          <p class="lede mt-6 max-w-xl">
            At MechaCraft, we build revenue-generating SaaS products, AI-powered systems engineered for scale, automation, and growth.
          </p>
          <div class="mt-10 flex flex-wrap items-center gap-x-8 gap-y-4">
            <a :href="MAILTO" class="btn cut">
              Start a conversation
              <svg class="size-4" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><path d="M3 8h10M9 4l4 4-4 4" /></svg>
            </a>
            <a href="#products" class="link">See our products</a>
          </div>
        </div>
        <div class="hidden md:col-span-4 md:block">
          <BrandLogo class="h-auto w-full" />
        </div>
      </section>

      <!-- Services -->
      <section id="services" class="border-t border-rule" aria-labelledby="services-title">
        <div class="shell py-20 md:py-28">
          <div class="grid gap-4 md:grid-cols-12 md:gap-6">
            <p class="eyebrow md:col-span-3">01 — What we do</p>
            <h2 id="services-title" class="heading max-w-3xl md:col-span-9">Production-ready SaaS platforms that generate revenue from day one.</h2>
          </div>
          <div class="mt-14 grid border-t border-rule md:grid-cols-3">
            <article
              v-for="(s, i) in services"
              :key="s.title"
              class="border-b border-rule py-8 md:border-b-0 md:border-l md:px-8 md:first:border-l-0 md:first:pl-0 md:last:pr-0"
            >
              <p class="text-sm text-ink-3 tabular-nums">{{ String(i + 1).padStart(2, '0') }}</p>
              <h3 class="mt-6 text-xl font-medium tracking-tight">{{ s.title }}</h3>
              <p class="mt-2 text-ink-2">{{ s.body }}</p>
              <ul class="mt-6 space-y-2 text-sm text-ink-2">
                <li v-for="item in s.items" :key="item" class="tick">{{ item }}</li>
              </ul>
            </article>
          </div>
        </div>
      </section>

      <!-- Products -->
      <section id="products" class="border-t border-rule" aria-labelledby="products-title">
        <div class="shell py-20 md:py-28">
          <div class="grid gap-4 md:grid-cols-12 md:gap-6">
            <p class="eyebrow md:col-span-3">02 — Our products</p>
            <h2 id="products-title" class="heading max-w-3xl md:col-span-9">Production platforms serving real customers.</h2>
          </div>
          <ul class="mt-14 border-t border-rule">
            <li v-for="p in products" :key="p.name" class="grid gap-3 border-b border-rule py-8 md:grid-cols-12 md:gap-6">
              <div class="md:col-span-3">
                <h3 class="text-xl font-medium tracking-tight">{{ p.name }}</h3>
                <p class="mt-1 text-sm text-ink-3">{{ p.category }}</p>
              </div>
              <p class="max-w-xl text-ink-2 md:col-span-6">{{ p.body }}</p>
              <div class="md:col-span-3 md:text-right">
                <a v-if="p.url" :href="p.url" target="_blank" rel="noopener noreferrer" class="link text-sm">
                  {{ p.domain }}
                  <svg class="size-3.5" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><path d="M5 11l6-6M6 5h5v5" /></svg>
                </a>
              </div>
            </li>
          </ul>
        </div>
      </section>

      <!-- Contact -->
      <section id="contact" class="shell pb-20 md:pb-28" aria-labelledby="contact-title">
        <div class="cut on-ink relative overflow-hidden px-8 py-14 md:px-16 md:py-20" style="--cut: 40px">
          <BrandLogo class="pointer-events-none absolute -right-10 -bottom-12 w-[26rem] max-w-[80%] text-paper opacity-[0.06]" />
          <div class="relative grid items-end gap-10 md:grid-cols-12">
            <div class="md:col-span-8">
              <p class="eyebrow">03 — Contact</p>
              <h2 id="contact-title" class="display mt-6">Work with us.</h2>
              <p class="lede mt-6 max-w-xl">We partner with founders, SMEs, and operators building scalable systems.</p>
            </div>
            <div class="flex flex-col items-start gap-4 md:col-span-4 md:items-end">
              <a :href="MAILTO" class="btn cut">
                Get in touch
                <svg class="size-4" viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5" aria-hidden="true"><path d="M3 8h10M9 4l4 4-4 4" /></svg>
              </a>
              <a :href="MAILTO" class="link">{{ EMAIL }}</a>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="border-t border-rule">
      <div class="shell grid gap-10 py-14 text-sm md:grid-cols-12 md:gap-6">
        <div class="space-y-4 md:col-span-4">
          <BrandLogo class="h-6 w-auto" />
          <div class="text-ink-3">
            <p class="text-ink">MechaCraft Sdn. Bhd.</p>
            <p>Company No. 202501021879 (1623292-T)</p>
            <p>TIN: C60102050020</p>
          </div>
        </div>
        <div class="md:col-span-4">
          <p>Main office (registered)</p>
          <p class="mt-2 leading-relaxed text-ink-3">
            1-19-03, Menara Bangkok Bank, Laman Sentral Berjaya, No. 105, Jalan Ampang, 50450 Kuala Lumpur, W.P. Kuala Lumpur.
          </p>
        </div>
        <div class="md:col-span-4">
          <p>New office</p>
          <p class="mt-2 leading-relaxed text-ink-3">
            Unit No. 20-01, Level 20, Menara Centara, No. 360 Jalan Tuanku Abdul Rahman, 50100 Kuala Lumpur, W.P. Kuala Lumpur, Malaysia
          </p>
        </div>
      </div>
      <div class="shell flex flex-wrap justify-between gap-4 border-t border-rule py-6 text-xs text-ink-3">
        <span>© {{ year }} MechaCraft Sdn. Bhd.</span>
        <a :href="MAILTO" class="nav">{{ EMAIL }}</a>
      </div>
    </footer>
  </div>
</template>
