
<script>
import Clock from '@/components/Clock.vue';
export default {
  name: 'App',
  components: {
    Clock
  }
}
</script>

<template>
  <div class="container">
    <div class="clock-container">
      <Clock color="green" />
      <Clock color="orange" />
      <Clock color="blue" />
      <Clock />
    </div>
  </div>
</template>

<style>
@font-face {
  font-family: "Alarm Clock";
  font-display: auto;
  src:
    local("alarm-clock"),
    url("/fonts/alarm-clock/alarm-clock.woff2") format("woff2"),
    url("/fonts/alarm-clock/alarm-clock.woff") format("woff"),
    url("/fonts/alarm-clock/alarm-clock.ttf") format("truetype");
}

body {
  background: linear-gradient(337deg, rgba(27, 36, 69, 1) 0%, rgba(27, 36, 69, 1) 48%, rgba(77, 70, 64, 1) 66%, rgba(79, 71, 64, 1) 75%, rgba(125, 102, 59, 1) 84%, rgba(253, 187, 45, 1) 100%) no-repeat center center fixed;
  display: flex;
  justify-content: center;
}


.clock-container {
  display: flex;
  flex-direction: column;
  gap: 30px;
  margin: 10px;
}
</style>
