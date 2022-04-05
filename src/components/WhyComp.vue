<template>
  <section class="why">
      <h2>Why My Courses?</h2>
      <div class="container">
      <div v-for="card in cardsList.slice(0,6)" :key="card.title" class="card">
        <div class="left">
          <font-awesome-icon v-if="card.useFontAwesome" class="icon" :icon="card.fontAwesomeName" />
          <img v-else :src="card.iconUrl">
        </div>
        <div class="right">
          <h3>{{ card.title }}</h3>
          <p>{{ card.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "WhyComp",
  data() {
    return {
      // Max 6 cards
      cardsList: [
        {
          title: "Entrepreneurship",
          desc: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa.",
          fontAwesomeName: ["fas","briefcase"],
          useFontAwesome: true,
          iconUrl: ""
        },
                {
          title: "Accelerated Learning",
          desc: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa.",
          fontAwesomeName: ["fas","rocket"],
          useFontAwesome: true,
          iconUrl: ""
        },
                {
          title: "Productivity",
          desc: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa.",
          fontAwesomeName: ["fas","thumbs-up"],
          useFontAwesome: true,
          iconUrl: ""
        },
                {
          title: "Life Coaching",
          desc: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem esse magnam sapiente dolorem ipsa nam, dolor quam. Aut voluptatum reprehenderit quia praesentium cupiditate, beatae quas quaerat velit maxime totam culpa.",
          fontAwesomeName: ["fas","gear"],
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
$sectionBackground: rgb(238, 242, 245);
$accentColor: #f2b71d;
$titleSize: 3rem;
$btnBackground: rgb(42, 62, 64);

.why {
  width: 100%;
  background-color: $sectionBackground;
  position: relative;
  text-align: center;
  padding: 100px 0;
}

.container {
  height: 100%;
  display: flex;
  text-align: center;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
}

.why-container {
  padding: 80px 0;
  flex-wrap: wrap;
  justify-content: center;
  display: flex;
  gap: 30px;
  width: 100%;
}

h2 {
  margin-bottom: 4rem;
  font-size: $titleSize;
  font-family: "Bitter", serif;
  width: 100%;
}

.card {
  width: calc(500px - 30px);
  background-color: rgb(255, 255, 255);
  display: flex;
  box-shadow: 1px 2px 15px 5px rgba(0,0,0,0.05);
  padding: 50px 30px;
  position: relative;
  text-align: left;
  
  &:hover{
    background-color: $accentColor;

    .icon{
      color: white;
    }
  }

  &::before{
    content: "";
    top: 0;
    left: 0;
    bottom: 0;
    width: 5px;
    background-color: $accentColor;
    position: absolute;
  }
  
  .right{
    width: 85%;
    padding-left: 20px;
  }

  .left{
    text-align: center;
    width: 15%;
  }
  .icon{
    font-size: 3rem;
  }

  h3 {
    margin-bottom: 15px;
  }
}
</style>
