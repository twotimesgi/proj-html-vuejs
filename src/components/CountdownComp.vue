<template>
  <div class="countdown">
    <div v-if="!this.toExpiration.isExpired">Days: {{ toExpiration.days }} Hours: {{ toExpiration.hours }} Minutes: {{ toExpiration.minutes }} Sec: {{ toExpiration.seconds }}</div>
    <div v-else>Expired!</div>
  </div>
</template>

<script>
export default {
  name: "CountdownComp",
  data(){
    return {
      expirationDate: "2022-04-01T17:54:00",
      toExpiration: {days: 0, hours: 0, minutes: 0, seconds: 0, isExpired: false}
    }
  },
  created(){
    const expirationDateParsed = new Date(this.expirationDate);
    const todayDate = new Date();
    if(expirationDateParsed > todayDate){
      const days = parseInt((expirationDateParsed - todayDate) / (1000 * 60 * 60 * 24));
      const hours = parseInt(Math.abs(expirationDateParsed - todayDate) / (1000 * 60 * 60) % 24);
      const minutes = parseInt(Math.abs(expirationDateParsed.getTime() - todayDate.getTime()) / (1000 * 60) % 60);
      const seconds = parseInt(Math.abs(expirationDateParsed.getTime() - todayDate.getTime()) / (1000) % 60); 
      this.toExpiration = {days, hours, minutes, seconds, isExpired: false};
      this.countdownStart();
    }else{
      this.toExpiration.isExpired = true;
    }
  },
  methods:{
    countdownStart(){
      let countdownInterval = setInterval(()=>{
        this.toExpiration.seconds--;
        if(this.toExpiration.seconds == 0){
          this.toExpiration.seconds = 60;
          this.toExpiration.minutes--;
        }
        if(this.toExpiration.minutes == 0){
          this.toExpiration.minutes = 60;
          this.toExpiration.hours--;
        }
        if(this.toExpiration.hours == 0){
          this.toExpiration.hours = 24;
          this.toExpiration.days--;
        }
        if(this.toExpiration.days == 0 && this.toExpiration.hours == 0 && this.toExpiration.minutes == 0 && this.toExpiration.seconds == 0){
          this.toExpiration.isExpired = true;
          clearInterval(countdownInterval);
        }
      },1000)
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
