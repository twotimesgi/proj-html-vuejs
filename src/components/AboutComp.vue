<template>
    <section class="about"> 
      <div class="container">
        <div class="left">
          <h3>Hey there, my name is John Doe. I'm the founder of the Brain Academy.</h3>
          <img src="../assets/sign.jpg">
        </div>
        <div class="right">
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus perferendis dolores optio quas excepturi obcaecati aperiam sequi itaque sunt expedita enim amet vel facere, magnam eum autem atque tempore suscipit!
          Possimus, esse soluta sapiente ut obcaecati dignissimos aliquam, sed reprehenderit in suscipit alias magni, at nostrum molestias praesentium cum ipsam itaque quasi corporis dicta deserunt tempora vel! Expedita, cupiditate minus?</p>
          </div>
      </div>
    </section>
</template>

<script>
export default {
  name: "AboutComp",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$titleSize: 1.6rem;
$numberSize: 5rem;
$textSize: 0.9rem;

.left, .right{
  width: 65%;
  padding: 150px 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  }

  .left{
    width: 35%;
  }

h3{
  font-family: "Bitter", serif;
  font-size: $titleSize;
  font-weight: 500;
  line-height: $titleSize * 1.5;
  margin-bottom: 3rem;
}

p{
  font-weight: 300;
  font-size: $textSize;
  line-height: $textSize*2;
}
</style>
