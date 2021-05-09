<template>
<div
  :class="{item, active}"
  @mouseover="(e) => setStyle(e)"
  @mouseout="setTop"
>
  <img
    :src="require('@/img/'+work.imgBig)"
    :alt="work.name"
    :style="{top, transition}"
  >
  <div class="item__content">
    <div class="item__h3">&laquo;{{ work.name }}&raquo;</div>
    <router-link to="#">Подробнее</router-link>
  </div>
</div>
</template>

<script>
export default {
  name: 'item',
  props: ['work'],
  data () {
    return {
      item: true,
      active: false,
      top: 0,
      transition: 'none'
    }
  },
  methods: {
    setStyle () {
      this.transition = `top ${this.work.imgBigHeight / 400}3s linear`
      this.top = `-${this.work.imgBigHeight - 280}px`
      this.active = !this.active
    },
    setTop () {
      this.top = '0'
      this.transition = 'none'
      this.active = !this.active
    }
  }
}
</script>

<style lang="sass">
.item:hover > .item__content
  display: block
.item.active > img
  filter: brightness(70%)
.item__content
  position: absolute
  height: 100%
  width: 100%
  top: 0
  left: 0
  padding: 10% 5% 0
  display: none
  & > a
    display: flex
    margin-top: 50%
    text-align: left
    color: #fff
    font-style: italic
    font-weight: 500
    border-bottom: 1px solid #fff
    padding-bottom: 5px
    padding-left: 7px
    width: 30%
    &:hover
      color: #c0daf8
      border-bottom: 1px solid #c0daf8
.item__h3
  font-size: 2em
  text-align: right
  color: #fff
  text-transform: uppercase
</style>
