<template>
  <div class="catalog-page">
    <HeaderLocal />
    <WorksBlock
    :worksBlocks="worksBlocks"
    />
    <Footer />
  </div>
</template>

<script>
import HeaderLocal from '../components/HeaderLocal'
import Footer from '../components/Footer'
import WorksBlock from '../components/Catalog/WorksBlock'
export default {
  name: 'Catalog',
  components: {
    HeaderLocal,
    Footer,
    WorksBlock
  },
  data () {
    return {
      worksBlocks: []
    }
  },
  methods: {
    addBlock (id, works) {
      const block = {
        id: id,
        display: 'none',
        works: works
      }
      this.worksBlocks.push(block)
    }
  },
  mounted () {
    this.$parent.getJson().then(data => {
      const works = []
      for (let i = 0; i < Math.ceil(data.length / 4); i++) {
        works.push(data.slice((i * 4), (i * 4) + 4))
      }
      works.forEach((el, index) => this.addBlock(index + 1, el))
      this.worksBlocks[0].display = 'flex'
      console.log(this.worksBlocks)
    })
  }
}
</script>

<style lang="sass">
.catalog-page
  background-color: #eee
  text-align: center
</style>
