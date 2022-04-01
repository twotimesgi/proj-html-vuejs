<template>
  <header>
    <div class="header-container">
      <div class="left">
        <img class="logo" src="../assets/logo.svg" />
      </div>
      <div class="right">
        <nav class="nav">
          <ul>
            <li class="new"><a href="">Test</a></li>
            <li><a href="">Test</a></li>
            <li class="active"><a href="">Test</a></li>
          </ul>
        </nav>
        <div class="social-icons">
          <font-awesome-icon :icon="['fab', 'linkedin']" />
          <font-awesome-icon :icon="['fab', 'instagram']" />
          <font-awesome-icon :icon="['fab', 'facebook']" />
          <font-awesome-icon :icon="['fab', 'twitter']" />
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComp",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$headerBackground: rgb(255, 255, 255);
$textColor: #252525;
$textSize: 1.2rem;
$iconSize: 1.2rem;
$accentColor: #f2b71d;

header {
  color: $textColor;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  border-bottom: 1px solid rgb(182, 182, 182);

  .header-container {
    width: 65%;
    background-color: $headerBackground;
    margin: 0 auto;
    padding: 40px 0;
    display: flex;
    justify-content: space-between;
  }

  .left,
  .right {
    align-items: center;
    display: flex;
  }

  li {
    display: inline;
    margin: 0 10px;
    font-size: $textSize;
    font-weight: 800;
    position: relative;

    &.new::after {
      content: "NEW";
      width: 25px;
      height: 10px;
      padding: 2px;
      top: -15px;
      right: -10px;
      font-size: 0.6rem;
      display: flex;
      justify-content: center;
      align-items: center;
      position: absolute;
      background-color: rgb(204, 0, 0);
      color: white;
      border-top-left-radius: 0.2rem;
      border-top-right-radius: 0.2rem;
      border-bottom-right-radius: 0.2rem;
      font-weight: 500;
    }

    &.active::after {
      content: "";
      width: 90%;
      height: 4px;
      background-color: $accentColor;
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
    }

    &.active::before {
      content: "";
      width: 0;
      height: 0;
      border-style: solid;
      border-width: 0 2.5px 4.3px 2.5px;
      border-color: transparent transparent $accentColor transparent;
      position: absolute;
      bottom: -7px;
      left: 50%;
      transform: translateX(-50%);
    }
  }

  a {
    color: $textColor;
    text-decoration: none;
  }

  .social-icons{
    margin-left: 50px;
    font-size: $iconSize;
    display: flex;
    gap: 15px;
  }

}
</style>
