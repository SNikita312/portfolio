<template>
  <div>
    <inner />
    <AboutBlock />
    <MiniGallery />
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Inner from '../components/HomePage/Inner.vue'
import AboutBlock from '../components/HomePage/AboutBlock'
import MiniGallery from '../components/HomePage/MiniGallery'
import Footer from '../components/Footer'

export default {
  name: 'Home',
  components: {
    Inner,
    AboutBlock,
    MiniGallery,
    Footer
  }
}
</script>
