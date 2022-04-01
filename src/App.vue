<template>
<div id="app">
  <header-comp />
</div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Bitter:wght@400;500;600;700&display=swap');

body{
  font-family: 'Bitter', serif;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
