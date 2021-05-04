<template>
  <div class="inner__content container">
    <div class="inner__text">
      <h1 class="inner__h1">Адаптивная</h1>
      <h1 class="inner__h1">Кроссбраузерная</h1>
      <h1 class="inner__h1">Верстка</h1>
      <p class="inner__p">под любые типы устройств</p>
      <p class="inner__p">Использование Flexbox и Grid</p>
      <h2 class="inner__h2">Верстка отдельных компонентов</h2>
      <p class="inner__p">Использование Vanilla.js, Vue.js</p>
    </div>
    <p></p>
    <p></p>
    <div class="mac-img">
      <img src="../../img/mac.png" alt="">
    </div>
    <div class="ipad-img">
      <img src="../../img/Ipad.png" alt="">
    </div>
    <div class="iphone-img">
      <img src="../../img/iphone.png" alt="">
    </div>
  </div>
</template>

<script>
export default {
  name: 'InnerContent'
}
</script>

<style lang="sass">
.inner__content
  height: 85%
  position: relative
  text-align: right
.mac-img,
.ipad-img,
.iphone-img
  position: absolute
.mac-img
  left: -15%
  top: 21%
.ipad-img
  left: 26%
  top: 33%
  transform: scale(1.3)
.iphone-img
  top: 42%
  left: 39%
.inner
  &__content
    display: flex
    flex-direction: row-reverse
  &__text
    padding-top: 100px
    color: #ffffff
    max-width: 45%
    font-family: 'Marmelad', sans-serif
  &__h1
    font-size: 3.5em
    font-weight: 400
    margin: 15px 0
  &__p
    font-size: 1.5em
  &__h2
    margin: 10px 0
    font-size: 1.7em
</style>
