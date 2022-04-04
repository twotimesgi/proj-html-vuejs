<template>
  <section class="counters">
      <div class="container">
      <div v-for="counter in countersList.slice(0,4)" :key="counter.label" class="counter">
        <div class="left">
          <font-awesome-icon v-if="counter.useFontAwesome" class="icon" :icon="counter.fontAwesomeName" />
          <img v-else :src="counter.iconUrl">
        </div>
        <div class="right">
          <div class="number">{{ counter.number }}</div>
          <div class="label">{{ counter.label }}</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "CountersComp",
  data() {
    return {
      // Max 4 counters
      countersList: [
        {
          label: "Online Learners",
          number: 3195,
          fontAwesomeName: ["fas","user-group"],
          useFontAwesome: true,
          iconUrl: ""
        },
                {
          label: "Video Courses",
          number: 23,
          fontAwesomeName: ["fas","film"],
          useFontAwesome: true,
          iconUrl: ""
        },
                {
          label: "Sliders & Images",
          number: 437,
          fontAwesomeName: ["fas","image"],
          useFontAwesome: true,
          iconUrl: ""
        },
                {
          label: "Excellent Reviews",
          number: 1440,
          fontAwesomeName: ["fas","thumbs-up"],
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
$accentColor: #f2b71d;
$labelColor: white;
$iconColor: white;

.counters {
  width: 100%;
  height: 30rem;
  background-image: url("../assets/countersbg.jpg");
  position: relative;
  text-align: center;
  padding: 100px 0;
}

.container {
  height: 100%;
  display: flex;
  text-align: center;
  flex-wrap: wrap;
  align-content: center;
  gap: 65px;
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
  font-size: 1rem;
  font-family: "Bitter", serif;
  width: 100%;
}

.counter {
  display: flex;
  text-align: left;
  gap: 10px;
  
  .right{
    width: 70%;
    display: flex;
    flex-direction: column;
    font-family: "Bitter", serif;
  }

  .left{
    text-align: center;
    width: 30;
  }

  .icon{
    font-size: 3.1rem;
    color: $iconColor;
  }

  .number{
    color: $accentColor;
    font-weight: 800;
    font-size: 1.6rem;
    margin-bottom: 5px;
  }

  .label {
   color: $labelColor;
   font-size: 0.9rem;
  }
}
</style>
