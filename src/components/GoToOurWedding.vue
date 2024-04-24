<template>
  <section class="w-full">
    <wave class="bg-slate-100" />
    <section class="container-section">
      <HeaderSection title="Go To Our Wedding" />
      <div class="mt-10 flex flex-wrap justify-center gap-3">
        <template v-for="(value, name, index) in countdown" :key="index">
          <div 
            data-aos="zoom-in"
            class="text-center w-4/12 bg-gray-100 p-2 rounded-lg">
            <p class="text-3xl text-green-500 mb-2">{{ value }}</p>
            <p class="kalam-font text-lg font-bold">{{ name }}</p>
          </div>
        </template>
      </div>
      <!--<div class="mt-12 text-center">
        <h1 
          data-aos="zoom-in"
          class="noto-sans-font text-green-500 text-2xl">Địa điểm tổ chức thành hôn</h1>
        <iframe 
          data-aos="zoom-in"
          class="w-10/12 mx-auto mt-4 mb-8" height="300" 
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1731.2061506719144!2d105.73512580431625!3d20.99897957043961!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3134538d76c46fd1%3A0x202e55c9074a606!2zVHJ1bmcgVMOibSBU4buVIENo4bupYyBT4buxIEtp4buHbiAmIFRp4buHYyBDxrDhu5tpIExvdWlzIFBhbGFjZQ!5e0!3m2!1svi!2s!4v1662404156182!5m2!1svi!2s" 
          frameborder="0" scrolling="no" 
          marginheight="0" marginwidth="0"></iframe>
        <h1 
          data-aos="zoom-in"
          class="noto-sans-font text-green-500 text-2xl">Địa điểm nhà gái</h1>
        <iframe 
          data-aos="zoom-in"
          class="w-10/12 mx-auto mt-4 mb-8" height="300" 
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3731.4470548915792!2d105.99472801542629!3d20.732666686159465!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3135b86c791a3871%3A0x0!2zMjDCsDQzJzU3LjYiTiAxMDXCsDU5JzQ4LjkiRQ!5e0!3m2!1svi!2s!4v1662404289288!5m2!1svi!2s" 
          frameborder="0" scrolling="no" 
          marginheight="0" marginwidth="0"></iframe>
      </div>-->
    </section>
  </section>
</template>

<script setup>

import { ref } from 'vue'
import HeaderSection from '@/components/HeaderSection.vue'
import wave from '@/assets/svg/wave.svg'

const countdown = ref(null)

// Handler for countdown
const createTimer = (target, container, cb) => {
   // target => UNIX time target
   // Container => variable for return result
   // cb => callback if countdown finish

   const now = new Date().getTime()
   const distance = target - now
   if ( distance > 0 ) {
     const days = Math.floor(distance / (1000 * 60 * 60 * 24));
     const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
     const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
     const seconds = Math.floor((distance % (1000 * 60)) / 1000);
      
     container.value = { days, hours, minutes, seconds }
     //alert(JSON.stringify(container))
      
     if (days === 0 && hours === 0 && minutes === 0 && seconds === 0 ) cb()
   } else {
     container.value = { days: 0, hours: 0, minutes: 0, seconds: 0 }
   } 
}

const timer = setInterval(() => {
  createTimer(new Date('2025-06-21 11:00').getTime(), countdown, () => {
    clearInterval(timer)
  })
}, 1000)

</script>
