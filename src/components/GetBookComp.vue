<template>
  <section class="get-book">
    <div class="container">
      <div class="left">
        <h3>Get My Exclusive Investing Book just for $19.50</h3>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. In eos perferendis unde neque earum natus quas aspernatur ipsum est hic tenetur, quis voluptatum voluptatem minima. Reprehenderit suscipit ducimus sint consequatur.</p>
        <a href="#"><img src="../assets/amazon.png" alt="Buy on Amazon"></a>
      </div>
      <div class="right">
      </div>
    </div>
  </section>
</template>

<script>

export default {
  name: "GetBookComp",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$accentColor: #f2b71d;
$titleSize: 2rem;
$textSize: 1.2rem;

.get-book{
  width: 100%;
  background-image: url("../assets/getbookbg.jpg");
  position: relative;
  height: 60vh;
}

.container { 
  height: 100%;
  display: flex;
  padding: 50px 0 0 0;
}

.left, .right{
  width: 50%;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.right{
  width: 50%;
  background-image: url("../assets/book.png");
  background-size: contain;
  height: 100%;
  background-repeat: no-repeat;
}

h3{
  font-size: $titleSize;
  color: $accentColor;
  margin-bottom: 2rem;
}

p{
  color: white;
  font-size: $textSize;
  font-style: italic;
  line-height: $textSize * 1.5;
  margin-bottom: 2rem;
}
</style>
