<template>
  <section class="w-full relative flex flex-col justify-center gap-3 bg-prewedding bg-center bg-cover h-screen">
    <wave class="absolute -bottom-1 left-0 right-0"/>
  </section>
</template>

<script setup>

import { computed } from 'vue'
import { useRoute } from 'vue-router' 
import wave from '@/assets/svg/wave.svg'

const route = useRoute()
let query = computed(() => route.query)

if (route.query.to === undefined) query = { to: 'Bạn' } 

</script>
