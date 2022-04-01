<template>
  <section>
    <div class="container">
      <div class="text-box">
        <div class="title"><h1>Start your Human <span class="hl">Revolution</span> today</h1></div>
        <div class="subTitle"><h2>A wonderful serenity has taken possession of my entire soul like these sweet mornings of spring which I enjoy with my whole heart.</h2></div>
      </div>
      <div class="cta-box">
        <div class="left"></div>
        <countdown-comp class="right"/>
      </div>
    </div>
  </section>
</template>

<script>
import CountdownComp from "./CountdownComp.vue";

export default {
  name: "HeroComp",
  components:{
    CountdownComp
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$headerBackground: rgb(255, 255, 255);
$textColor: #252525;
$accentColor: #f2b71d;
$titleSize: 3.5rem;
$subtitleSize: 1.2rem;

section{
  width: 100%;
  background-image: url("../assets/hero.jpg");
  background-repeat: no-repeat;
  height:  70vh;
  background-size: cover;
  position: relative;
}

.container{
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
  height: 100%;
}

.text-box{
  width: 50%;
  height: 300px;

  h1{
    margin-bottom: 1.5rem;
    color: $textColor;
    font-size: $titleSize;
    font-family: 'Bitter', serif;
  }

  h2{
    font-weight: 300;
    font-size: $subtitleSize;
  }

  .hl{
    color: $accentColor;
  }
}

.cta-box{
  background-color: $accentColor;
  width: 80%;
  max-width: 65rem;
  height: 13rem;
  position: absolute;
  bottom: -75px;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 0.7rem;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 30px;
}

.left, .right{
  width: 50%;
}
</style>
