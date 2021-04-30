<template>
<section class="about-block container">
  <div class="about-block__content">
  <h1 class="about-block__title">Обо мне</h1>
  <p class="about-block__text">Меня зовут Никита Дмитриевич. Я&nbsp;занимаюсь Фронт Энд разработкой.<br>Комуникабельный и&nbsp;пунктуальный.
    <br>Основной целью для себя в&nbsp;этой специальности вижу качественное и&nbsp;своевременное выполнение поставленной задачи.
    Все свободное время уделяю веб разработке. Мне нравится то&nbsp;&mdash; что я&nbsp;делаю, и&nbsp;готов к&nbsp;любым не&nbsp;предвиденным ситуациям.
    Активно развиваюсь в&nbsp;этой сфере и&nbsp;слежу за&nbsp;ее&nbsp;развитием. Знаю Html, CSS, JS. Более подробно с&nbsp;моими навыками и&nbsp;умениями можно
    ознакомится в&nbsp;разделе <router-link to="/about">&laquo;Обо мне&raquo;</router-link>, а&nbsp;так&nbsp;же просмотрев мои работы на&nbsp; <a href="https://github.com/brave312guide">GitHub</a> или в&nbsp;разделе <router-link to="/about">&laquo;Мои работы&raquo;</router-link>.</p>
  <ul class="about-block__social">
    <li><a href="https://t.me/brave_guide"><i class="fab fa-telegram"></i></a></li>
    <li><a href="https://github.com/brave312guide"><i class="fab fa-github"></i></a></li>
    <li><a href="https://api.whatsapp.com/send?phone=380663566405&text=%D0%94%D0%BE%D0%B1%D1%80%D1%8B%D0%B9%20%D0%B4%D0%B5%D0%BD%D1%8C%2C%20%D1%8F%20%D0%BF%D0%BE%20%D0%BF%D0%BE%D0%B2%D0%BE%D0%B4%D1%83..."><i class="fab fa-whatsapp"></i></a></li>
  </ul>
  </div>
  <img src="../img/photo.jpg" alt="photo" class="about-block__photo">
</section>
</template>

<script>
export default {
  name: 'AboutBlock'
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
  &__social
    display: flex
    margin-top: 20px
    & > li
      margin-right: 20px
      transition: color .1s linear
      &:active
        transform: scale(.9)
    & > li > a
      font-size: 40px
      color: #87baf6
      transition: color .1s linear
      &:hover
        color: #34495e
      &:active
        color: #ccc
</style>
