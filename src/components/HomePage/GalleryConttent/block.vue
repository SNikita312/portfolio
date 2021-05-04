<template>
<div>
  <item v-for="work in block.works" v-bind:work="work" v-bind:class="work.classObj" v-bind:key="work.id"></item>
</div>
</template>

<script>
import item from './item'
export default {
  name: 'block',
  props: ['block'],
  components: {
    item
  }
}
</script>

<style>

</style>
