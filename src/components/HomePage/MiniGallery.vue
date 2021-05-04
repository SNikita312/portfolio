<template>
<section class="mini-gallery">
  <div class="container">
    <h1 class="mini-gallery__title">Последние работы</h1>
  </div>
    <div class="mini-gallery__carousel">
      <div class="mini-gallery__inner">
        <block v-for="block in workBlocks" v-bind:block="block" v-bind:key="block.id" v-bind:class="block.classObj"></block>
      </div>
      <div class="mini-gallery__arrLeft"><i class="fa fa-chevron-left"></i></div>
      <div class="mini-gallery__arrRight"><i class="fa fa-chevron-right"></i></div>
  </div>
</section>
</template>

<script>
import block from './GalleryConttent/block'
export default {
  name: 'MiniGallery',
  components: {
    block
  },
  data () {
    return {
      workBlocks: [
        {
          id: 1,
          classObj: {
            'mini-gallery__flex': true,
            active: true
          },
          works: [
            {
              id: 1,
              name: 'brand',
              img: 'proj1.jpg',
              classObj: {
                item: true,
                active: false
              }
            },
            {
              id: 2,
              name: 'game',
              img: 'proj2.jpg',
              classObj: {
                item: true,
                active: false
              }
            },
            {
              id: 3,
              name: 'fengo',
              img: 'proj3.jpg',
              classObj: {
                item: true,
                active: false
              }
            }
          ]
        },
        {
          id: 2,
          classObj: {
            'mini-gallery__flex': true,
            active: false
          },
          works: [
            {
              id: 1,
              name: 'brand',
              img: 'proj1.jpg',
              classObj: {
                item: true,
                active: false
              }
            },
            {
              id: 2,
              name: 'game',
              img: 'proj2.jpg',
              classObj: {
                item: true,
                active: false
              }
            },
            {
              id: 3,
              name: 'fengo',
              img: 'proj3.jpg',
              classObj: {
                item: true,
                active: false
              }
            }
          ]
        }
      ]
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
    overflow: hidden
  &__flex
    width: 100%
    height: 100%
    display: none
    justify-content: space-between
    &.active
      display: flex
.item
  margin: 10px
  height: 93%
  width: 33%
  overflow: hidden
  &.active > img
    transition: transform 3s linear
    transform: translateY(-70%)
</style>
