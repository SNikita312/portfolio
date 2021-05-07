<template>
  <div class="about-page">
    <div class="top">
      <Header />
    </div>
    <Summary />
    <Skills />
    <Additionally/>
    <Footer />
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import Summary from '../components/AboutBlocks/Summary'
import Skills from '../components/AboutBlocks/Skills'
import Footer from '../components/Footer'
import Additionally from '../components/AboutBlocks/Additionally'

export default {
  name: 'About',
  components: {
    Header,
    Summary,
    Skills,
    Footer,
    Additionally
  }
}
</script>

<style lang="sass">
.top
  background-color: #000
.about-page
  display: grid
  height: 100vh
  grid-template-rows: 100px 1fr 1fr
</style>
