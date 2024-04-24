<style scoped>

.frame {
  @apply w-4/12 rotate-180;
}

.input-wrapper {
  @apply w-full flex flex-wrap gap-1 mb-3;
}

label {
  @apply w-full text-green-500 text-xl;
}

input, textarea, select, option {
  @apply w-full px-2 py-3 rounded-lg bg-white duration-300 focus:border-green-500 text-gray-700;
}

</style>

<template>
  <section class="w-full mb-12 relative bg-slate-100 pb-0">
    <wave class="bg-slate-100 rotate-180"/>
    <section class="container-section">
      <HeaderSection title="LOVE YOU" />
      <!-- Gift Section -->
      <Gift></Gift>
      <!-- Frames -->
      <div class="w-full items-center flex justify-between mt-6">
        <img class="frame" src="@/assets/frame.png" alt="frame">
        <p class="text-sm">huanpd&copy;2025</p>
        <img class="frame" src="@/assets/frame-mirror.png" alt="frame">
      </div>
    </section>
  </section>
</template>

<script setup>

import { computed, reactive, ref } from 'vue'
import axios from 'axios'
import HeaderSection from '@/components/HeaderSection.vue'
import Gift from '@/components/Gift.vue'
import wave from '@/assets/svg/wave.svg'
</script>
