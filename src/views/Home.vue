<template>
  <div>
    <inner />
    <AboutBlock />
    <MiniGallery />
  </div>
</template>

<script>
// @ is an alias to /src
import Inner from '../components/HomePage/Inner.vue'
import AboutBlock from '../components/HomePage/AboutBlock'
import MiniGallery from '../components/HomePage/MiniGallery'

export default {
  name: 'Home',
  components: {
    Inner,
    AboutBlock,
    MiniGallery
  }
}
</script>
