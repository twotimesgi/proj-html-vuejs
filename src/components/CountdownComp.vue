<template>
    <div class="countdown" v-if="!this.toExpiration.isExpired">
      <div class="tile">
        <div class="number">{{ toExpiration.days }}</div>
        <div class="label">Days</div>
      </div>
      <div class="tile">
        <div class="number">{{ toExpiration.hours }}</div>
        <div class="label">Hours</div>
      </div>
      <div class="tile">
        <div class="number">{{ toExpiration.minutes }}</div>
        <div class="label">Minutes</div>
      </div>
      <div class="tile">
        <div ref="seconds" class="number">{{ toExpiration.seconds }}</div>
        <div class="label">Seconds</div>
      </div>
    </div>
    <div class="expired" v-else>Expired!</div>
</template>

<script>
export default {
  name: "CountdownComp",
  data() {
    return {
      expirationDate: "2022-04-1T19:04:50",
      toExpiration: {
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0,
        isExpired: false,
      },
    };
  },
  created() {
    const expirationDateParsed = new Date(this.expirationDate);
    const todayDate = new Date();
    if (expirationDateParsed > todayDate) {
      const days = parseInt(
        (expirationDateParsed - todayDate) / (1000 * 60 * 60 * 24)
      );
      const hours = parseInt(
        (Math.abs(expirationDateParsed - todayDate) / (1000 * 60 * 60)) % 24
      );
      const minutes = parseInt(
        (Math.abs(expirationDateParsed.getTime() - todayDate.getTime()) /
          (1000 * 60)) %
          60
      );
      const seconds = parseInt(
        (Math.abs(expirationDateParsed.getTime() - todayDate.getTime()) /
          1000) %
          60
      );
      this.toExpiration = { days, hours, minutes, seconds, isExpired: false };
      this.countdownStart();
    } else {
      this.toExpiration.isExpired = true;
    }
  },
  methods: {
    countdownStart() {
      let countdownInterval = setInterval(() => {
        this.toExpiration.seconds--;

        if (this.toExpiration.seconds == 0 && this.toExpiration.minutes != 0) {
          this.toExpiration.seconds = 60;
          this.toExpiration.minutes--;
        }

        if (this.toExpiration.minutes == 0 && this.toExpiration.hours != 0) {
          this.toExpiration.minutes = 60;
          this.toExpiration.hours--;
        }

        if (this.toExpiration.hours == 0 && this.toExpiration.days != 0) {
          this.toExpiration.hours = 24;
          this.toExpiration.days--;
        }

        if (
          this.toExpiration.seconds == 0 &&
          this.toExpiration.minutes == 0 &&
          this.toExpiration.hours == 0 &&
          this.toExpiration.days == 0
        ) {
          clearInterval(countdownInterval);
          this.toExpiration.isExpired = true;
        }
      }, 1000);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$numberColor: rgb(255,255,255);
$labelColor: rgb(0,0,0);
$numberSize: 4rem;
$labelSize: 1.2rem;

.expired{
  font-size: 4rem;
  text-align: center;
}

.countdown{
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  gap: 20px;
  width: 100%;
  height: 100%;
}

.tile{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .number{
    font-size: $numberSize;
    color: $numberColor;
    font-weight: 800;
  }
  .label{
    font-family: 'Bitter', serif;
    color: $labelColor;
    font-size: $labelSize;
  }
}
</style>
