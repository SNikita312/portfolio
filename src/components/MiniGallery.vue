<template>
<section class="mini-gallery">
  <div class="container">
    <h1 class="mini-gallery__title">Последние работы</h1>
  </div>
    <div class="mini-gallery__carousel">
      <div class="mini-gallery__inner">
        <div v-bind:class="classObject" @mouseover="classObject.active = true" @mouseleave="classObject.active = false">
          <img src="../img/proj1.jpg" alt="">
        </div>
        <div v-bind:class="classObject">
          <img src="../img/proj2.jpg" alt="">
        </div>
        <div class="item">
          <img src="../img/proj3.jpg" alt="">
        </div>
      </div>
      <div class="mini-gallery__arrLeft"><i class="fa fa-chevron-left"></i></div>
      <div class="mini-gallery__arrRight"><i class="fa fa-chevron-right"></i></div>
  </div>
</section>
</template>

<script>
export default {
  name: 'MiniGallery',
  data () {
    return {
      classObject: {
        item: true,
        active: false
      }
    }
  }
}
</script>

<style lang="sass">
.mini-gallery
  padding: 75px 0
  background-color: #eeeeee
  text-align: center
  width: 100%
  &__title
    font-size: 2.25em
    font-weight: 700
    letter-spacing: -0.01em
    color: #34495e
    margin-bottom: 20px
  &__carousel
    width: 100%
    height: 300px
    position: relative
    background-color: #e5e5e5
  &__arrLeft,
  &__arrRight
    position: absolute
    top: 45%
    color: #34495e
    font-size: 30px
    &:hover
      cursor: pointer
  &__arrLeft
    left: 13%
  &__arrRight
    right: 13%
  &__inner
    width: 70%
    height: 100%
    margin: 0 15%
    position: relative
    overflow: hidden
    display: flex
    justify-content: space-between
.item
  margin: 10px
  height: 93%
  width: 33%
  overflow: hidden
  &.active > img
    transition: transform 3s linear
    transform: translateY(-70%)
</style>
