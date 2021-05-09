<template>
<section class="skills">
  <div class="skills__content container">
    <h1 class="skills__title">Ключевые навыки:</h1>
    <article class="skills__skill">
      <img src="../../img/html.png" alt="">
      <h3 class="skills__h3">HTML5</h3>
      <ul class="skills__list">
        <li class="skills__li">Использование методологии БЭМ</li>
        <li class="skills__li">Использование семантических элементов</li>
        <li class="skills__li">Bootstrap</li>
      </ul>
    </article>
    <article class="skills__skill">
      <img src="../../img/css.png" alt="">
      <h3 class="skills__h3">CSS3</h3>
      <ul class="skills__list">
        <li class="skills__li">Медиа-запросы (адаптивная верстка)</li>
        <li class="skills__li">Препроцессинг (Sass, Scss, Less)</li>
        <li class="skills__li">Flexbox, Grid  позиционирование</li>
        <li class="skills__li">CSS Анимация</li>
        <li class="skills__li">Bootstrap</li>
      </ul>
    </article>
    <article class="skills__skill">
      <img src="../../img/js.png" alt="">
      <h3 class="skills__h3">Vanilla JavaScript</h3>
      <ul class="skills__list">
        <li class="skills__li">ECMAScript 6, ECMAScript 5</li>
        <li class="skills__li">NodeJS на базовом уровне</li>
        <li class="skills__li">Тестирование и отладка</li>
        <li class="skills__li">Простой back-end на JS</li>
        <li class="skills__li">AJAX, Fetch API</li>
        <li class="skills__li">ООП JS</li>
        <li class="skills__li">DOM</li>
      </ul>
    </article>
    <article class="skills__skill">
      <img src="../../img/vue.png" alt="">
      <h3 class="skills__h3">Vue.js</h3>
      <ul class="skills__list">
        <li class="skills__li">Работа с компонетами</li>
        <li class="skills__li">Vue Route</li>
        <li class="skills__li">Vue CLI</li>
      </ul>
    </article>
    <article class="skills__skill">
      <img src="../../img/git.png" alt="">
      <h3 class="skills__h3">Git</h3>
      <ul class="skills__list">
        <li class="skills__li">Основные навыки работы с системой контроля версий Git</li>
      </ul>
    </article>
  </div>
</section>
</template>

<script>
export default {
  name: 'Skills'
}
</script>

<style lang="sass">
.skills
  background-color: #eeeeee
  padding: 50px 0
  margin-top: 30px
  &__title
    color: #3e5f7f
    width: 100%
    text-align: center
    margin-bottom: 30px
  &__content
    display: flex
    flex-wrap: wrap
    justify-content: center
  &__skill
    display: flex
    flex-direction: column
    align-items: center
    width: 33%
    padding: 20px 5px 0
  &__h3
    margin: 10px 0 15px
    color: rgba(0, 0, 0, 0.66)
  &__list
    width: 70%
  &__li
    margin-bottom: 10px
    text-align: center
    font-size: 15px
    color: #3e5f7f
</style>
