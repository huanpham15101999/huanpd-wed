<template>
  <section class="w-11/12 mx-auto mt-16 text-center">
    <h1 data-aos="zoom-in"
      class="kalam-font text-green-500 text-2xl">Gift For Us</h1>
    <p data-aos="zoom-in" class="text-xs mt-4">
      Lời chúc của bạn là món quà vô cùng ý nghĩa đối với chúng tôi
    </p>
    <section class="mt-10">
      <template v-for="(wallet, x) in wallets" :key="x">
        <div data-aos="zoom-in" class="w-10/12 mx-auto mb-4 p-5 bg-white rounded-xl">
          <img :src="wallet.thumb" :alt="wallet.platform" class="w-5/12 mx-auto mb-3">
          <p class="text-xs">{{ wallet.name }}</p>
          <Clipboard :content="wallet.number"></Clipboard>
        </div>
      </template>
    </section>
  </section>
</template>

<script setup>

import Clipboard from '@/components/Clipboard.vue'

const wallets = [
  {
    thumb: 'wallets/vpbank.jpg',
    platform: 'VPBANK',
    name: 'PHAM DINH HUAN',
    number: '35615101999'
  },
  {
    thumb: 'wallets/vpbank.jpg',
    platform: 'VPBANK',
    name: 'MAI PHAM MAI ANH',
    number: '235447703'
  }
]
</script>
