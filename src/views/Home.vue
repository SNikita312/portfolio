<template>
  <div>
    <inner />
    <AboutBlock />
    <MiniGallery />
  </div>
</template>

<script>
// @ is an alias to /src
import Inner from '../components/Inner.vue'
import AboutBlock from '../components/AboutBlock'
import MiniGallery from '../components/MiniGallery'

export default {
  name: 'Home',
  components: {
    Inner,
    AboutBlock,
    MiniGallery
  }
}
</script>
