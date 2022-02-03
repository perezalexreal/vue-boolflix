<template>
  <div id="app">
<header-box/>
<main-container/>
  </div>
</template>

<script>
import HeaderBox from './components/HeaderBox.vue'
import MainContainer from './components/MainContainer.vue'

export default {
  name: 'App',
  components: {
    HeaderBox,
    MainContainer
  }
}
</script>

<style lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}


</style>
