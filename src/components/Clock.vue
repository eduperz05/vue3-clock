
<script>
import { zeroPad } from "@/modules/zeroPad.js"
export default {
  mounted() {
    setInterval(() => {
      this.timeUpdate();
    }, 1000);
  },
  updated() {

  },
  props: {
    color: {
      type: String,
      default: "red",
      required: false
    }
  },
  data() {
    return {
      hours: "--",
      minutes: "--",
      seconds: "--",
      mode: "pm",
      textColor: this.color
    }
  },
  methods: {
    timeUpdate() {
      const date = new Date();
      this.hours = zeroPad(date.getHours());
      this.minutes = zeroPad(date.getMinutes());
      this.seconds = zeroPad(date.getSeconds());
      this.mode = this.hours <= 12 ? "am" : "pm";
    }
  }
}
</script>

<template>
  <div class="clock-box">
    <div class="clock-screen">
      <div class="hours"> {{ hours }} </div>
      <div class="delimiter">:</div>
      <div class="minutes"> {{ minutes }} </div>
      <div class="delimiter">:</div>
      <div class="seconds"> {{ seconds }} </div>
      <div class="mode"> {{ mode }}</div>
    </div>
  </div>
</template>

<style>
.clock-box {
  padding: 25px;
  margin: 10px;
  background: rgb(14, 14, 14);
  background: linear-gradient(36deg, rgb(37, 37, 37) 0%, rgb(120, 120, 120) 100%);
  border: black solid 2px;
  border-radius: 4%;
  transform: scale(1.7, 1);
  box-shadow: 50px 70px 50px 10px rgba(0, 0, 0, 0.6);
}

.clock-screen {
  display: inline-flex;
  justify-content: center;
  align-items: flex-end;
  padding: 20px;
  background-color: black;
  border-radius: 4%;
  font-size: 4rem;
  font-family: "Alarm Clock", sans-seriff;
  color: v-bind("textColor");
}

.mode {
  margin-bottom: 10px;
  font-size: 50%;
}
</style>