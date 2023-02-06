<template>
  <img class="slide" :src="slides" alt="slide">



</template>

<script>

export default ({
  name: 'Slider',
  props: {
    slides: {
      type: String,
      required: true,
    }
  },

})
</script>
<style scoped>
.slide {
  width: 20%;
  height: 20%;
}
</style>
