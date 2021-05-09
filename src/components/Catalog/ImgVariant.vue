<template>
  <div :class="classObj">
    <img :src="require('@/img/Catalog/'+img)" alt="">
  </div>
</template>

<script>
export default {
  name: 'ImgVariant',
  props: {
    img: String
  },
  data () {
    return {
      classObj: {
        active: false
      }
    }
  }
}
</script>

<style scoped>

</style>
