<script setup>
import { MARK } from '@/brand.js'
</script>

<template>
  <svg :viewBox="`0 0 ${MARK.width} ${MARK.height}`" fill="currentColor" fill-rule="evenodd" aria-hidden="true">
    <path :d="MARK.d" />
  </svg>
</template>
