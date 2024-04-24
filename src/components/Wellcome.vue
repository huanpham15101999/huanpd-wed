<style scoped>
.frame {
  @apply absolute w-6/12 md:w-4/12 z-0;
}

@keyframes backOutUp-custom {
  0% {
    -webkit-transform: scale(1);
    transform: scale(1);
    opacity: 1;
  }

  20% {
    -webkit-transform: translateY(0px) scale(0.7);
    transform: translateY(0px) scale(0.7);
    opacity: 0.7;
  }

  100% {
    -webkit-transform: translateY(-700px) scale(0.7);
    transform: translateY(-100%) scale(0.7);
    opacity: 0.7;
  }
}
.close-page {
  animation: backOutUp-custom .5s 1s forwards;
}

</style>

<template>
  <section :class="isOpenInvitation ? 'close-page' : ''" class="w-full h-full	bg-slate-100 fixed inset-0 grid place-items-center z-50 bg-texture bg-cover">
    <!-- Frames -->
    <img class="frame top-0 left-0 animate__animated animate__fadeInLeft" src="@/assets/frame-mirror.png" alt="frame">
    <img class="frame top-0 right-0 animate__animated animate__fadeInRight" src="@/assets/frame.png" alt="frame">
    <img class="frame bottom-0 right-0 rotate-180" src="@/assets/frame-mirror.png" alt="frame">
    <img class="frame bottom-0 left-0 rotate-180" src="@/assets/frame.png" alt="frame">
    <!-- Frames -->
    <!-- Wedding couple -->
    <div class="w-10/12 text-center text-xs md:text-lg lg:text-xl">
      <!-- Decoration -->
      <img src="@/assets/decoration-asset-1.png" class="animate__animated animate__swing w-6/12 md:w-3/12 mx-auto">
      
      <div class="mt-5 animate__animated animate__zoomInUp">
        <p class="dancing-script-font text-2xl lg:text-3xl my-4 text-black-600">{{ weddingDate }}</p>
        <h1 class="dancing-script-font text-4xl lg:text-5xl my-4 text-green-600">{{ couples.join(' & ') }}</h1>
        <p class="dancing-script-font text-2xl lg:text-3xl my-4 text-black-600"> Trân trọng kính mời </p>
       <!-- CTA -->
        <button 
          type="buton" 
          @click="openInvitation"
          class="w-6/12 md:w-3/12 text-sm md-text-lg mt-12 font-medium z-50 border border-blue-500 text-blue-500 bg-light p-2 rounded-full pointer active:scale-90 hover:bg-blue-500 hover:text-gray-100 duration-300">
          <i class="fa-solid fa-book-open mr-1"></i>
          Mở thiệp
       </button>
       <!-- CTA -->
      </div>
    </div>
    <!-- Wedding couple -->
    </section>
</template>

<script setup>

import { ref } from 'vue'
import { useState } from '@/stores/state.js'

const state = useState()

const couples = ref(['Huấn', 'Mai Anh'])
const weddingDate = ref('Save the date')

const isOpenInvitation = ref(false)

const openInvitation = () => {
  isOpenInvitation.value = true
  state.isAudioPlay = true
}

</script>
