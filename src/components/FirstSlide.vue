<template>
    <img class="img-slide" src="../assets/first-slide.jpg" alt="">
</template>

<script>
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