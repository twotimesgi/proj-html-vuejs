<template>
<div id="app">
  <header-comp />
  <main>
    <hero-comp />
    <about-comp />
    <courses-comp />
    <get-book-comp />
    <why-comp />
    <counters-comp />
    <testimonials-comp />
  </main>
</div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import HeroComp from './components/HeroComp.vue'
import AboutComp from './components/AboutComp.vue'
import CoursesComp from './components/CoursesComp.vue'
import GetBookComp from './components/GetBookComp.vue'
import WhyComp from './components/WhyComp.vue'
import CountersComp from './components/CountersComp.vue'
import TestimonialsComp from './components/TestimonialsComp.vue'



export default {
  name: 'App',
  components: {
    HeaderComp,
    HeroComp,
    AboutComp,
    CoursesComp,
    GetBookComp,
    WhyComp,
    CountersComp,
    TestimonialsComp
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Bitter:wght@400;500;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');
$accentColor: #f2b71d;

body{
  font-family: 'Roboto', sans-serif;
}

.container{
    width: 65%;
    min-width: 1000px;
    margin: 0 auto;
    display: flex;
}

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
