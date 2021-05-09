<template>
<article class="catalog__item" @mouseover="stopAnim" @mouseleave="startAnim">
  <div class="catalog__item-img">
    <div class="catalog__item-imgBig">
      <img
        :src="require('@/img/Catalog/'+imgDefault)"
        :alt="item.name"
      >
    </div>
    <div
      v-if="item.imgSmall.length"
      class="catalog__item-variants"
    >
      <div
        v-for="(img, index) in item.imgSmall"
        :key="index+1"
        :data-id="index"
        class="catalog__item-imgSmall"
        @click="changeBigImg(index)"
        ref="ar"
      >
        <img :src="require('@/img/Catalog/'+img)" :alt="index">
      </div>
    </div>
  </div>
  <div class="catalog__item-content">
    <h3 class="catalog__item-title" v-html="item.title"></h3>
    <h5 v-if="item.notAdaptive" class="catalog__item-adaptive">Проект не адаптивный</h5>
    <h5 v-else class="catalog__item-adaptive true">Проект адаптивный</h5>
    <p class="catalog__item-total" v-html="item.pageInfo"></p>
    <p class="catalog__item-total" v-html="item.about"></p>
    <p v-if="item.optional" class="catalog__item-optional" v-html="item.optional"></p>
    <a class="catalog__item-btn" href="">Подробнее</a>
  </div>
</article>
</template>

<script>
export default {
  name: 'CatalogItem',
  props: { item: Object, bigImg: String, variantsBig: Array },
  data () {
    return {
      imgDefault: this.bigImg,
      clearInt: false,
      idx: null,
      change: null
    }
  },
  methods: {
    changeBigImg (index) {
      this.imgDefault = this.variantsBig[index]
      this.$refs.ar.find(el => el.classList.contains('active')).classList.remove('active')
      this.$refs.ar[index].classList.add('active')
      this.idx = index
    },
    stopAnim () {
      clearInterval(this.change)
    },
    startAnim () {
      this.change = setInterval(() => {
        if (this.idx === this.variantsBig.length) {
          this.idx = 0
        }
        this.changeBigImg(this.idx)
        this.idx++
      }, 2000)
    }
  },
  mounted () {
    if (this.variantsBig) {
      this.$refs.ar[0].classList.add('active')
      this.idx = this.$refs.ar.indexOf(this.$refs.ar.find(el => el.classList.contains('active')))
      this.change = setInterval(() => {
        if (this.idx === this.variantsBig.length) {
          this.idx = 0
        }
        this.changeBigImg(this.idx)
        this.idx++
      }, 2000)
    }
  }
}
</script>

<style lang="sass">
.catalog__item
  display: flex
  justify-content: space-between
  margin-bottom: 100px
  padding-bottom: 20px
  width: 45%
  &-img
    height: 100%
    display: flex
    flex-direction: column
    justify-content: flex-end
  &-imgBig
    max-height: 250px
    width: 216px
    overflow: hidden
    box-shadow: -1px 2px 8px 0px rgba(0, 0, 0, 0.2)
  &-imgSmall
    max-height: 65px
    overflow: hidden
    transition: all .2s linear
    box-shadow: -1px 2px 8px 0px rgba(0, 0, 0, 0.2)
    &:hover
      cursor: pointer
      transform: translateY(-10px)
      box-shadow: -1px 12px 8px 0px rgba(0, 0, 0, 0.2)
    &.active
      transform: translateY(-10px)
      box-shadow: -1px 12px 8px 0px rgba(0, 0, 0, 0.2)
  &-variants
    margin-top: 50px
    display: flex
    justify-content: space-between
    align-items: flex-end
  &-title
    color: #4a4a7b
  &-content
    display: flex
    flex-direction: column
    width: 50%
    padding: 0 10px
  &-adaptive
    padding: 5px 15px
    margin: 20px auto
    background-color: #801d1d
    border-radius: 13px
    color: #ffffff
    &.true
      background-color: #067635
  &-total
    font-size: .8em
    color: #326d97
    font-weight: 700
    margin-bottom: 15px
    text-align: left
    & > span
      color: #616161
      margin-left: 10px
      font-weight: 400
      text-align: center
  &-optional
    font-size: .8em
    color: #e53737
    font-weight: 700
    border-radius: 30px
    margin-bottom: 10px
    text-align: left
    & > span
      color: #b67070
      margin-left: 10px
      font-weight: 400
  &-btn
    background-color: #244863
    margin: 20px auto 0
    padding: 15px 25px
    font-size: 1em
    color: #fff
    border-radius: 10%
    transition: all .2s linear
    &:hover
      color: #a2c6f1
      transform: scale(.97)
    &:active
      transform: scale(.95)
</style>
