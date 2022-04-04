<template>
  <section class="courses">
    <div class="container">
      <h2>New Courses</h2>
      <div class="courses-container">
      <div v-for="item in coursesList.slice(0,nOfCoursesShowed)" :key="item.title" class="card">
        <div :class="item.isSpecial ? 'special':''" class="img-box">
          <img :src="item.imgUrl">
          <div class="overlay">{{ item.price }}</div>
        </div>
        <h3 class="title">{{ item.title }}</h3>
        <div class="category">{{ item.category }}</div>
        <div class="info-container">
          <div class="item"><font-awesome-icon  class="icon" :icon="['fas', 'signal']" />{{ item.difficulty }}</div>
          <div class="item"><font-awesome-icon  class="icon" :icon="['fas', 'list']" />{{ item.lectures }} Lectures</div>
          <div class="item"><font-awesome-icon class="icon" :icon="['far', 'clock']" />{{ item.hours }} hours</div>
        </div>
      </div>
      </div>
      <button v-if="nOfCoursesShowed < coursesList.length" @click="nOfCoursesShowed+=3">LOAD MORE</button>
    </div>
  </section>
</template>

<script>

export default {
  name: "CoursesComp",
  data(){
    return {
      nOfCoursesShowed: 3,
      coursesList: [
        {
          title: "How to be a DJ? Make Electronic Music",
          imgUrl: require("../assets/course1.jpeg"),
          category: "Eletronic",
          isSpecial: true,
          difficulty: "Advanced",
          lectures: 8,
          hours: 6,
          price: "$59"
      },
      {
          title: "Nvidia and UE4 Technologies Practice",
          imgUrl: require("../assets/course2.png"),
          category: "Nvidia",
          isSpecial: true,
          difficulty: "Advanced",
          lectures: 8,
          hours: 6,
          price: "$79"
      },
      {
          title: "Fashion Photography from professional",
          imgUrl: require("../assets/course-3.jpeg"),
          category: "Fashion",
          isSpecial: true,
          difficulty: "Advanced",
          lectures: 6,
          hours: 6,
          price: "$29"
      },
      {
          title: "Design Instruments for Communication",
          imgUrl: require("../assets/course-4.jpeg"),
          category: "Communication",
          isSpecial: true,
          difficulty: "Intermediate",
          lectures: 6,
          hours: 6,
          price: "$29"
      },
      {
          title: "Make your Concept Right and Beautiful",
          imgUrl: require("../assets/course-5.jpg"),
          category: "Art",
          isSpecial: true,
          difficulty: "Intermediate",
          lectures: 6,
          hours: 6,
          price: "$79"
      },
      {
          title: "Road Bike Manual or How to Be a Champion.",
          imgUrl: require("../assets/course-6.jpeg"),
          category: "Bicycling",
          isSpecial: true,
          difficulty: "Beginner",
          lectures: 6,
          hours: 6,
          price: "$89"
      }
      ]
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$sectionBackground: rgb(238,242,245);
$accentColor: #f2b71d;
$titleSize: 3rem;
$btnBackground: rgb(42, 62, 64);

.courses {
  width: 100%;
  background-color: $sectionBackground;
  position: relative;
}

.container { 
  height: 100%;
  display: block;
  padding: 100px 0;
  text-align: center;
}

.courses-container{
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

button{
  background-color: $accentColor;
  color: white;
  font-family: "Bitter", serif;
  padding: 1rem 1.5rem;
  border: none;
  margin-top: 2rem;
  border-radius: 2rem;
}

button:hover{
  filter: brightness(0.8);
}

.card{
  width: 300px;
  background-color: rgb(255,255,255);
  border: 1px solid rgb(209, 209, 209);

  .img-box{
    width: 100%;
    height: 200px;
    position: relative;
  }

  .overlay{
    display: none;
    inset: 0;
    position: absolute;
    background-color: rgba(0, 0, 0,0.3);
    justify-content: center;
    align-items: center;
    color: white;
    font-size: 1.2rem;
    font-weight: 800;
    font-family: "Bitter", serif;
  }

  .img-box:hover .overlay{
    display: flex;
  }

  .img-box::after{
    content: "SPECIAL";
    background-color: $accentColor;
    position: absolute;
    padding: 5px;
    top: 0.5rem;
    right: 0.5rem;
    color: white;
    border-radius: 0.3rem;
    font-family: "Bitter", serif;
    font-size: 0.6rem;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  img{
    height: 100%;
    width: 100%;
    object-fit: cover;
  }

  .title{
    text-align: center;
    margin: 25px 15px 10px 15px;
  }

  .category{
    width: 100%;
    text-align: center;
    opacity: 0.5;
    font-size: 0.8rem;
    margin-bottom: 2rem;
  }

  .info-container{
    margin: 0 10px;
    padding: 20px 0;
    display: flex;
    justify-content: space-around;
    border-top: 1px solid rgb(230, 230, 230);

    .item{
      display: flex;
      gap: 5px;
      font-size: 0.8rem;
      opacity: 0.7;
      color: rgba(0, 0, 0,0.8)
    }

    .icon{
      color: $accentColor;
    }
  }

}

</style>
