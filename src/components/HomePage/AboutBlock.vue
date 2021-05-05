<template>
<section class="about-block container">
  <div class="about-block__content">
  <h1 class="about-block__title">Обо мне</h1>
  <p class="about-block__text">Меня зовут Никита Дмитриевич. Я&nbsp;занимаюсь Frontend-разработкой.<br>Коммуникабельный и&nbsp;пунктуальный.
    <br><br>Основной целью для себя в&nbsp;этой специальности вижу качественное и&nbsp;своевременное выполнение поставленной задачи.
    Все свободное время уделяю веб-разработке. Мне нравится то, что я&nbsp;делаю,&nbsp;готов к&nbsp;любым непредвиденным ситуациям.
    Активно совершенствуюсь в&nbsp;этой сфере и&nbsp;слежу за&nbsp;ее&nbsp;развитием. Знаю Html, CSS, JS. <br><br>Более подробно с&nbsp;моими навыками и&nbsp;умениями можно
    ознакомиться в&nbsp;разделе <router-link to="/about">&laquo;Обо мне&raquo;</router-link>, а&nbsp;также просмотрев мои работы на&nbsp; <a href="https://github.com/brave312guide">GitHub</a> или в&nbsp;разделе <router-link to="/about">&laquo;Мои работы&raquo;</router-link>.</p>
    <SocialLinks></SocialLinks>
  </div>
  <img src="../../img/photo.jpg" alt="photo" class="about-block__photo">
</section>
</template>

<script>
import SocialLinks from '../SocialLinks/SocialLinks'
export default {
  name: 'AboutBlock',
  components: {
    SocialLinks
  }
}
</script>

<style lang="sass">
.about-block
  display: flex
  padding: 170px 0
  justify-content: space-between
  align-items: flex-start
  &__title
    font-weight: 700
    letter-spacing: -0.01em
    color: #34495e
    margin-bottom: 20px
  &__content
    width: 60%
  &__photo
    border-radius: 50%
  &__text
    font-size: 18px
    line-height: 30px
    font-weight: 400
    color: #34495e
    & > a
      color: #87baf6
      transition: color .2s linear
      &:hover
        color: #34495e

</style>
