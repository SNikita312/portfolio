<template>
  <header class="header container">
    <div class="logo">
      <router-link to="/">Портфолио</router-link>
    </div>
    <nav>
      <ul class="menu">
        <router-link
          to="/"
          custom
          v-slot="{ href, route, navigate, isActive, isExactActive }"
        >
          <li
            :class="[isActive && 'router-link-active', isExactActive && 'active', 'menu__li']"
          >
            <a :href="href" class="menu__link">Главная</a>
          </li>
        </router-link>
        <router-link
          to="/about"
          custom
          v-slot="{ href, route, navigate, isActive, isExactActive }"
        >
          <li
            :class="[isActive && 'router-link-active', isExactActive && 'active', 'menu__li']"
          >
            <a :href="href" class="menu__link">Обо мне</a>
          </li>
        </router-link>
        <router-link
          to="/catalog"
          custom
          v-slot="{ href, route, navigate, isActive, isExactActive }"
        >
          <li
            :class="[isActive && 'router-link-active', isExactActive && 'active', 'menu__li']"
          >
            <a :href="href" class="menu__link">Мои работы</a>
          </li>
        </router-link>
        <router-link
          to="/contacts"
          custom
          v-slot="{ href, route, navigate, isActive, isExactActive }"
        >
          <li
            :class="[isActive && 'router-link-active', isExactActive && 'active', 'menu__li']"
          >
            <a :href="href" class="menu__link">Контакты</a>
          </li>
        </router-link>
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
  transition: all .1s linear
  &:hover
    transform: scale(1.05)
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
      & > a
        border-bottom: 2px solid #fff
        &:hover
          border-bottom: 2px solid #87baf6
    &:hover
      transform: translateY(-3px)
      color: #87baf6
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
    &:hover
      border-bottom: 2px solid #87baf6
      color: #87baf6
</style>
