<script>
import { ref, onMounted } from 'vue'
export default {
  name: 'DigitalClock',
  setup(){
    let hours = ref(0);
    let minutes = ref(0);
    let seconds = ref(0);
    const setTime=()=> {
      const date = new Date();
      let h = date.getHours();
      let m = date.getMinutes();
      let s = date.getSeconds();
      h = h <= 9 ? `${h}`.padStart(2, 0) : h;
      m = minutes <= 9 ? `${m}`.padStart(2, 0) : m;
      s = s <= 9 ? `${s}`.padStart(2, 0) : s;
      hours.value = h;
      minutes.value = m;
      seconds.value = s;
    }

    const showLocalTime = function(){
        setInterval(() => setTime(), 1000)
    };

    onMounted(() => {
      showLocalTime()
    })

    return{
      hours,
      minutes,
      seconds
    }

  }

}
</script>

<template>
  <div class="container">
    <div class="LCD">
      <div class="hours">{{ hours }}</div>
      <div class="divider">:</div>
      <div class="minutes">{{ minutes }}</div>
      <div class="divider">:</div>
      <div class="seconds">{{ seconds }}</div>
    </div>
  </div>
</template>

<style scoped>
.LCD {
  display: flex;
}
.LCD > div {
  font-family: "alarm clock";
  font-size: x-large;
}
</style>