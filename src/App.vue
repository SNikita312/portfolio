<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: 'Roboto Condensed', sans-serif;
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  &:focus {
    outline: none;
  }
}
a {
  text-decoration: none;
}
li {
  list-style-type: none;
}
</style>
