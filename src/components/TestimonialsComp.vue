<template>
  <section class="testimonials">
      <h2>What Students Say?</h2>
      <div class="container">
      <div class="imgs-box">
        <font-awesome-icon  @click="selectedIndex != 0 ? selectedIndex-- : null" class="arrow-left" :icon="['fas', 'chevron-left']" />
        <font-awesome-icon  @click="selectedIndex != testimonialsList.length - 1 ? selectedIndex++ : null" class="arrow-right" :icon="['fas', 'chevron-right']" />
        <img v-for="(testimonial, index) in testimonialsList.slice(0,6)" @click="selectedIndex = index" :class="index == selectedIndex ? 'selected' : ''" :src="testimonial.imgUrl" :key="testimonial.name" class="testimonial-img">
      </div>
      <div class="testimonial-info">
        <h3>{{ testimonialsList[selectedIndex].title }}</h3>
        <div>
          <font-awesome-icon  v-for="(n,index) in Math.floor(testimonialsList[selectedIndex].vote)" :key="index" class="star" :icon="['fas', 'star']" />
          <font-awesome-icon  v-for="(n,index) in 5 - Math.floor(testimonialsList[selectedIndex].vote)" :key="index" class="star" :icon="['far', 'star']" />
          </div>
        <p>{{ testimonialsList[selectedIndex].desc.slice(0,875) }}{{ testimonialsList[selectedIndex].desc.length > 874 ? "..." : ""}}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "TestimonialsComp",
  data() {
    return {
      // Max 6 testimonials
      // Desc length max 875 chars
      testimonialsList: [
        {
          title: "Paints of the future",
          vote: 5,
          desc: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa.",
          imgUrl: require("../assets/test-1.jpg")
        },
        {
          title: "Wow! I'm really impressed.",
          vote: 5,
          desc: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa.",
          imgUrl: require("../assets/test-2.jpg")
        },
        {
          title: "Great course!",
          vote: 4.2,
          desc: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa.",
          imgUrl: require("../assets/test-3.jpg")
        },
      ],
    selectedIndex: 0
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$sectionBackground: rgb(255, 255, 255);
$accentColor: #f2b71d;
$titleSize: 3rem;
$btnBackground: rgb(42, 62, 64);

.testimonials {
  width: 100%;
  background-color: $sectionBackground;
  position: relative;
  text-align: center;
  padding: 100px 0;
}

.imgs-box{
  width: 100%;
  position: relative;
  display: flex;
  gap: 20px;
  justify-content: center;
  align-items: center;

  .arrow-left, .arrow-right{
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 2rem;
    opacity: 0.5;
  }
  .arrow-left{
    left: 50px;
  }
  .arrow-right{
    right: 50px;
  }

  .testimonial-img{
  width: 75px;
  height: 75px;
  border-radius: 50%;

  &.selected{
    width: 100px;
    height: 100px;
  }
}
}

.container {
  height: 100%;
  display: flex;
  text-align: center;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.star{
  color: $accentColor;
}

h2 {
  margin-bottom: 4rem;
  font-size: $titleSize;
  font-family: "Bitter", serif;
  width: 100%;
}

h3{
    margin: 20px 0 10px 0;
    font-family: "Bitter", serif; 
    font-size: 1.6rem;
    font-weight: 00;
}

p{
  margin-top: 40px;
  font-weight: 300;
  font-size: 1.1rem;
  line-height: calc(1.1rem * 2);
  height: 15rem;
  overflow: hidden;
}
</style>
