<template>
    <section class="fixed left-0 right-0 bottom-0">
        <section class="container-section flex justify-around p-3">
            <template v-for="nav in navs" :key="nav.id">
                <i  @click="navAction(nav.id)"
                    :class="nav.icon" 
                    class="pointer active:scale-65 duration-300 text-lg text-red-500"></i>
            </template>
        </section>
    </section>
</template>

<script setup>

const navs = [
    { icon: 'fa fa-home', id: '#mainCover'},
    { icon: 'fa-solid fa-children', id: '#groomAndBride'},
    { icon: 'fa-solid fa-hourglass', id: '#goToOurWedding'},
    { icon: 'fa-solid fa-photo-film', id: '#ourGallery'},
    { icon: 'fa-solid fa-book-bookmark', id: '#guestBook'},
]

const emits = defineEmits(['navChange'])

const navAction = id => emits('navChange', id)

</script>
