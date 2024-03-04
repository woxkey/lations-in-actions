<template>
    <img class="img-slide" :src="url" alt="">
</template>

<script>
import FirstSlide from '../assets/first-slide.jpg'
export default {
    name: 'FirstSlide',
    props: ['url'],
}
</script>

<style scoped>
.img-slide {
  height: 275px;
  width: 158px;
}
</style>