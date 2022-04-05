<template>
  <footer>
    <div class="container">
    <div class="item">
      <h3>About</h3>
      <p>
        Masterstudy is Education WordPress theme featured by Learning Management System (LMS) for online education.
        Developed by StylemixThemes.
      </p>
      <div class="social-icons">
        <a
          v-for="icon in socialIcons.slice(0, 5)"
          :href="icon.url"
          :key="icon.url"
        >
          <font-awesome-icon
            v-if="icon.useFontAwesome"
            :icon="['fab', icon.fontAwesomeName]"
          />
          <img v-else :src="icon.iconUrl" :alt="icon.alt" />
        </a>
      </div>
    </div>
    <div class="item">
      <h3>Contact</h3>
      <p>
        USA, California 20, First Avenue, California
      </p>
      <p>
        Tel.: +1 212 458 300 32
        Fax: +1 212 375 24 14
      </p>
      <p>info@masterstudy.com</p>
    </div>
    <div class="item">
      <h3>Pages</h3>
      <ul>
        <li v-for="item in footerItems" :key="item.url">
          <a :href="item.url">{{ item.text }}</a>
        </li>
      </ul>
    </div>
    <div class="item">
      <h3>Blog</h3>
      <div v-for="post in postsList.slice(0, 2)" :key="post.title" class="article">
        <img :src="post.imgUrl" class="article-img">
        <div class="article-data">
          <h4><a :href="post.url">{{ post.title.slice(0, 60) }}</a></h4>
          <span> – {{ new Date(post.date).toLocaleDateString('en-US', { year: 'numeric', month: 'long', day: 'numeric' }) }}</span>
        </div>
      </div>
    </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "FooterComp",
  data() {
    return {
      footerItems: [
        {
          text: "Blog",
          url: "#",
        },
        {
          text: "Home",
          url: "#",
        },
        {
          text: "Shortcodes",
          url: "#",
        },
        {
          text: "Courses",
          url: "#",
        },
        {
          text: "Membership",
          url: "#",
        },
        {
          text: "Typography",
          url: "#",
        },
      ],
      socialIcons: [
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
      ],
      //post.title max length 60 chars
      postsList: [
        {
          title: 'Our main target is to "Developing Yourself as a Leader"',
          imgUrl: require("../assets/blog-article-1.jpeg"),
          date: "2022-02-19T19:04:50",
          url: "#"
        },
        {
          title: "Those Other College Expenses You Aren't Thinking About",
          imgUrl: require("../assets/blog-article-2.jpeg"),
          date: "2022-02-19T19:04:50",
          url: "#"
        }
      ]
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$footerBackground: #f2b71d;
$textColor: rgba(0,0,0,0.8);
$textSize: 1.2rem;
$iconSize: 1.2rem;

footer {
  padding: 100px;
  color: $textColor;
  width: 100%;
  background-color: $footerBackground;
  border-bottom: 1px solid rgb(209, 209, 209);

.item{
  width: 25%;
}

.container{
  gap: 40px;
}

h3{
 font-size: 1.5rem;
  margin-bottom: 20px;
  font-family: "Bitter", serif;
  text-transform: uppercase;
}

p, li{
  margin: 15px 0;
  line-height: 1.5rem;
  font-weight: 300;
}

ul{
  display: flex;
  flex-wrap: wrap;
  gap: 10px 80px;

}

li{
  margin: 0;
  width: calc(50% - 40px);
}

.article{
  display: flex;
  gap: 10px;
  margin-top: 20px;

  h4{
    font-family: "Bitter", serif;
  }
  .article-img{
    width: 75px;
    height: 75px;
  }
}

  a {
    color: $textColor;
    text-decoration: none;
    transition: 0.1s color linear;
  }

  .social-icons {
    margin-top: 10px;
    font-size: $iconSize;
    display: flex;
    gap: 15px;
  }
}
</style>
