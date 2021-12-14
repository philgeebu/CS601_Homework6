<template>
  <img :src="pictureHover" @mouseover="hover = true" @mouseleave="hover = false" :alt="pictureHoverAlt">
</template>

<script>
  export default {
    name: 'HoverPicture',
    data() {
      return {
        hover: false,
        altText: ''
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
      },
      pictureHoverAlt() {
        if (this.hover == true) {
          return this.picture.picture_b_alt
        } else {
          return this.picture.picture_a_alt
        }
      },
    },
  }
</script>