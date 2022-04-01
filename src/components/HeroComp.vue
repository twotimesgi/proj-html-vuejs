<template>
  <section class="hero">
    <div class="container">
      <div class="text-box">
        <div class="title">
          <h1>
            Start your Human <span class="hl-accent">Revolution</span> today
          </h1>
        </div>
        <div class="subTitle">
          <h2>
            A wonderful serenity has taken possession of my entire soul like
            these sweet mornings of spring which I enjoy with my whole heart.
          </h2>
        </div>
      </div>
      <div class="cta-box">
        <div class="left">
          <h3>
            <span class="hl-white">Limited Sale:</span> All courses with 55% off
          </h3>
          <div class="input-container">
            <input type="text" placeholder="Enter your E-mail" />
            <button>SUBSCRIBE</button>
          </div>
        </div>
        <countdown-comp class="right" />
      </div>
    </div>
  </section>
</template>

<script>
import CountdownComp from "./CountdownComp.vue";

export default {
  name: "HeroComp",
  components: {
    CountdownComp,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$headerBackground: rgb(255, 255, 255);
$textColor: #252525;
$accentColor: #f2b71d;
$titleSize: 3.5rem;
$subtitleSize: 1.2rem;
$ctaSize: 1.5rem;
$btnBackground: rgb(42, 62, 64);

.hero {
  width: 100%;
  background-image: url("../assets/hero.jpg");
  background-repeat: no-repeat;
  height: 70vh;
  background-size: cover;
  position: relative;
}

.container {
  flex-direction: column;
  justify-content: center;
  align-items: flex-end;
  height: 100%;
}

.text-box {
  width: 50%;
  height: 300px;

  h1 {
    margin-bottom: 1.5rem;
    color: $textColor;
    font-size: $titleSize;
    font-family: "Bitter", serif;
  }

  h2 {
    font-weight: 300;
    font-size: $subtitleSize;
  }
}
.hl-accent {
  color: $accentColor;
}

.hl-white {
  color: white;
}

.cta-box {
  background-color: $accentColor;
  width: 65%;
  height: 13rem;
  position: absolute;
  bottom: -75px;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 0.7rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

.left,
.right {
  width: 50%;
  padding: 50px;
}

.left {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 30px;

  h3 {
    font-family: "Bitter", serif;
    font-size: $ctaSize;
  }

  input {
    padding: 15px;
    box-shadow: 0px 5px 10px 10px rgba(0, 0, 0, 0.1);
    border: none;
    border-radius: 3rem;
    width: 100%;
  }

  button {
    position: absolute;
    right: 0;
    top: 0;
    padding: 15px;
    border: 0px;
    background-color: $btnBackground;
    color: white;
    font-family: "Bitter", serif;
    border-radius: 3rem;
  }

  button:hover {
    filter: brightness(0.8);
  }

  .input-container {
    width: 100%;
    position: relative;
  }
}
</style>
