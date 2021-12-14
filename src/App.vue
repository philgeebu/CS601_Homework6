<template>
  <div class="app">
    <header>
      <h1>Phil's Assignment 6</h1>
    </header>
    <section>
      <p>Instructions: hover over the images to see a close-up.</p>
      <HoverPicture v-for="picture in hoverList" :key="picture.id" :picture="picture" class="picture" />
    </section>
  </div>
</template>

<script>
  import hoverJson from '@/assets/hover_pictures.json'
  import HoverPicture from '@/components/HoverPicture.vue'

  export default {
    name: 'App',
    data() {
      return {
        hoverList: hoverJson
      }
    },
    components: {
      HoverPicture
    }
  }
</script>

<style>
  body {
    font-family: sans-serif;
    margin: 0;
    padding: 0;
  }

  h1,
  p {
    text-align: center;
  }

  .picture {
    max-width: 500px;
    border-radius: 7px;
    cursor: zoom-in;
  }

  section {
    border-radius: 7px;
    gap: 1rem;
    margin: 0 auto;
    display: flex;
    flex-flow: column wrap;
    align-content: center;
    box-shadow: 5px 5px 10px purple;
    max-width: 960px;
    padding: 2em;
    margin-bottom: 30px;
  }
</style>