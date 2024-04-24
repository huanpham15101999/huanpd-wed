<template>
  <section 
    class="w-full">
    <img data-aos="zoom-in" class="w-8/12 mx-auto rounded-full border-4 border-slate-200 ring-2 ring-green-600" :src="source.thumb" :alt="source.thumb">
    <div data-aos="slide-up" class="mt-4 w-full text-center text-slate-800 text-sm">
      <p class="mb-3 mt-1 text-green-500 dancing-script-font text-2xl">{{ source.name }}</p>
      <p class="mb-3 mt-1">Bố: {{ source.parents[0] }}  &  Mẹ: {{ source.parents[1] }}</p>
      <p class="mb-3 mt-1">{{ source.address }}</p>
      <div class="flex gap-3 justify-center mt-3">
        <template v-for="(item, x) in source.sosmed" :key="x">
          <a target="_blank" :href="item.link"><i :class="item.icon" class="text-xl"></i></a>
        </template>
      </div>
    </div>
  </section>
</template>

<script setup>

const props = defineProps({
  source: {
    type: Object,
    default: { name: 'fulan' }
  }
})

</script>
