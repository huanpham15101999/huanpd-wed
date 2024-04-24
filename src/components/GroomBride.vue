<template>
  <section class="w-full bg-slate-100">
    <wave class="rotate-180" />
    <section class="container-section">
      <HeaderSection title="Bride & Groom" />
      <div class="w-10/12 mx-auto text-center text-sm text-slate-800" >
        <p 
          data-aos="zoom-in"
          class="kalam-font text-2xl text-green-500 mb-3">
          Happy Together!
        </p>
        <!--<p data-aos="zoom-in"
          class="dancing-script-font text-xl text-black-500 mb-3">
          Yêu mà không cưới phí hoài thanh xuân
        </p>-->
      </div>
      <Profile />
      <Timelines />
    </section>
  </section>
</template>

<script setup>

import HeaderSection from '@/components/HeaderSection.vue'
import Profile from '@/components/Profile.vue'
import Timelines from '@/components/Timelines.vue'
import wave from '@/assets/svg/wave.svg'

</script>
