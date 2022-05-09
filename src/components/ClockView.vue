<script>
export default {
  name: "ClockView",
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
      let hours = (date.getHours());
      let minutes = (date.getMinutes());
      let seconds = (date.getSeconds());
      this.hours = hours;
      this.minutes = minutes;
      this.seconds = seconds;
    }
  }
}
</script>

<template>
  <h1>Reloj Vue</h1>
  <div class="container">
    <div class="clock">
      <div class="hours">{{ hours }} :</div>
      <div class="minutes">{{ minutes }} :</div>
      <div class="seconds">{{ seconds }}</div>
    </div>
  </div>
</template>

<style scoped>
.clock {
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "alarm clock";
  font-size: x-large
}
</style>