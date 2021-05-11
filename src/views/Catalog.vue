<template>
  <div class="catalog-page">
    <HeaderLocal />
    <div v-if="loading" class="loader">
      <h2>Подождите загрузку контента</h2>
      <div class="snippet" data-title=".dot-falling">
        <div class="stage">
          <div class="dot-falling"></div>
        </div>
      </div>
    </div>
    <WorksBlock
    v-else
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
      worksBlocks: [],
      loading: true
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
    })
    setTimeout(() => {
      this.loading = false
    }, 4000)
  }
}
</script>

<style lang="sass">
.catalog-page
  background-color: #eee
  text-align: center
.loader
  display: flex
  width: 100%
  justify-content: center
  align-items: center
  height: 62vh
  & > h2
    margin-right: 30px
    color: #5427dc
.dot-falling
  position: relative
  left: -9999px
  width: 10px
  height: 10px
  border-radius: 5px
  background-color: #5427dc
  color: #5427DCFF
  box-shadow: 9999px 0 0 0 #5427DCFF
  animation: dotFalling 1s infinite linear
  animation-delay: .1s
.dot-falling::before, .dot-falling::after
  content: ''
  display: inline-block
  position: absolute
  top: 0
.dot-falling::before
  width: 10px
  height: 10px
  border-radius: 5px
  background-color: #5427DCFF
  color: #5427DCFF
  animation: dotFallingBefore 1s infinite linear
  animation-delay: 0s
.dot-falling::after
  width: 10px
  height: 10px
  border-radius: 5px
  background-color: #5427DCFF
  color: #5427DCFF
  animation: dotFallingAfter 1s infinite linear
  animation-delay: .2s
@keyframes dotFalling
  0%
    box-shadow: 9999px -15px 0 0 rgba(152, 128, 255, 0)

  25%,
  50%,
  75%
    box-shadow: 9999px 0 0 0 #5427DCFF
  100%
    box-shadow: 9999px 15px 0 0 rgba(152, 128, 255, 0)
@keyframes dotFallingBefore
  0%
    box-shadow: 9984px -15px 0 0 rgba(152, 128, 255, 0)
  25%,
  50%,
  75%
    box-shadow: 9984px 0 0 0 #5427DCFF
  100%
    box-shadow: 9984px 15px 0 0 rgba(152, 128, 255, 0)
@keyframes dotFallingAfter
  0%
    box-shadow: 10014px -15px 0 0 rgba(152, 128, 255, 0)
  25%,
  50%,
  75%
    box-shadow: 10014px 0 0 0 #5427DCFF
  100%
    box-shadow: 10014px 15px 0 0 rgba(152, 128, 255, 0)
</style>
