<script>
export default {
  name: "DigitalClock",
  data() {
    return {
      //Inicializamos las variables a 0
      hours: 0,
      minutes: 0,
      seconds: 0
    }
  },
  mounted() {
    setInterval(() => this.setTime(), 1000)
  },
  methods: {
    setTime() {
      const date = new Date();
      let hours = date.getHours();
      let minutes = date.getMinutes();
      let seconds = date.getSeconds();
      if (minutes >= 60) {
        minutes = 0;
        hours = hours + 1;
      }
      if (seconds >= 60) {
        seconds = 0;
        minutes = minutes + 1;
      }
      this.hours = hours;
      this.minutes = minutes;
      this.seconds = seconds;
    }
  }
}
</script>

<template>
  <h1>Digital Clock</h1>
  <div class="container">
    <div class="clock">
      <div class="hours">{{ hours }}</div>
      <div class="divider">:</div>
      <div class="minutes">{{ minutes }}</div>
      <div class="divider">:</div>
      <div class="seconds">{{ seconds }}</div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.clock {
  font-family: "alarm clock";
  font-size: x-large
}
</style>