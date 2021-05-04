<template>
<div>
  <img v-bind:src="require('@/img/'+work.img)" v-bind:alt="work.name">
</div>
</template>

<script>
export default {
  name: 'item',
  props: ['work']
}
</script>

<style>

</style>
