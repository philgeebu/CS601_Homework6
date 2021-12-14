<template>
  <img :src="pictureHover" @mouseover="hover = true" @mouseleave="hover = false">
</template>

<script>
  export default {
    name: 'HoverPicture',
    data() {
      return {
        hover: false,
      }
    },
    props: ['picture'],
    computed: {
      pictureHover() {
        if (this.hover == true) {
          return '/img/' + this.picture.picture_b_file
        } else {
          return '/img/' + this.picture.picture_a_file
        }
      }
    },
  }
</script>