<template>
  <header>
    <div class="container">
      <div class="left">
        <img class="logo" src="../assets/logo.svg" />
      </div>
      <div class="right">
        <nav class="nav">
          <ul>
            <li v-for="item in menuItems.slice(0,5)" :key="item.title" :class="[item.new ? 'new': '', item.active ? 'active':'']"><a :href="item.url">{{ item.title }}</a></li>
          </ul>
        </nav>
        <div class="social-icons">
          <a v-for="icon in socialIcons.slice(0,5)" :href="icon.url" :key="icon.url">
            <font-awesome-icon v-if="icon.useFontAwesome" :icon="['fab', icon.fontAwesomeName]" />
            <img v-else :src="icon.iconUrl" :alt="icon.alt">
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  name: "HeaderComp",
  data() {
    return {
      // Max 5 items
      menuItems: [
        {
          title: "Courses",
          url: "#",
          new: false,
          active: false
        },
        {
          title: "Course Formats",
          url: "#",
          new: false,
          active: false
        },
        {
          title: "Add Course",
          url: "#",
          new: true,
          active: false
        },
        {
          title: "Pages",
          url: "#",
          new: false,
          active: false
        },
        {
          title: "Demos",
          url: "#",
          new: false,
          active: true
        },
      ],
      // Max 5 items
      socialIcons: [
        {
          alt: "linkedin",
          url: "#",
          fontAwesomeName: "linkedin",
          useFontAwesome: true,
          iconUrl: ""
        },
        {
          alt: "instagram",
          url: "#",
          fontAwesomeName: "instagram",
          useFontAwesome: true,
          iconUrl: ""
        },
        {
          alt: "facebook",
          url: "#",
          fontAwesomeName: "facebook",
          useFontAwesome: true,
          iconUrl: ""
        },
        {
          alt: "twitter",
          url: "#",
          fontAwesomeName: "twitter",
          useFontAwesome: true,
          iconUrl: ""
        },
      ]
    };
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
  top: 0;
  left: 0;
  padding: 50px 0;
  right: 0;
  background-color: $headerBackground;
  border-bottom: 1px solid rgb(209, 209, 209);

  .container{
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
    font-family: 'Bitter', serif;

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
    transition: 0.1s color linear;
  }

  a:hover {
    color: $accentColor;
  }

  .social-icons {
    margin-left: 50px;
    font-size: $iconSize;
    display: flex;
    gap: 15px;
  }
}
</style>
