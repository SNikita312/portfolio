<template>
  <header class="header container">
    <div class="logo">
      <router-link to="/">Портфолио</router-link>
    </div>
    <nav>
      <ul class="menu">
        <li class="menu__li"><router-link class="menu__link" to="/">Главная</router-link></li>
        <li class="menu__li"><router-link class="menu__link" to="/about">Обо мне</router-link></li>
        <li class="menu__li"><router-link class="menu__link" to="/about">Мои работы</router-link></li>
        <li class="menu__li"><router-link class="menu__link" to="/about">Контакты</router-link></li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="sass">
.container
  max-width: 1150px
  margin: 0 auto
.header
  height: 100px
  display: flex
  justify-content: space-between
  align-items: center
.logo
  & > a
    font-family: 'Lobster', cursive
    font-size: 36px
    line-height: 30px
    font-weight: 700
    color: #ffffff
.menu
  display: flex
  &__li
    margin-right: 30px
    transition: all .1s linear
    &.active
      transform: translateY(-3px)
    &:hover
      transform: translateY(-3px)
    &:last-child
      margin-right: 0
  &__link
    font-size: 18px
    line-height: 30px
    font-weight: 400
    color: #ffffff
    transition: all .1s linear
    text-transform: uppercase
    padding-bottom: 5px
    &.active
      border-bottom: 2px solid #fff
    &:hover
      border-bottom: 2px solid #fff
</style>
