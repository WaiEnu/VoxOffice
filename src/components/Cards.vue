<script>
import { ref } from 'vue'
export default {
  name: 'Cards',
  setup(){
    const max = 4;
    let card = ref(0);
    card.value = Math.floor(Math.random() * max) + 1;
		const shuffle = () => (card.value = Math.floor(Math.random() * max) + 1);

    return{
      card,
      shuffle
    }

  }

}
</script>

<template>
  <div class="container">
    <div class="LCD">
      <div>{{ card }}</div>
      <div><button @click="shuffle()">shuffle</button></div>
    </div>
  </div>
</template>

<style scoped>
.LCD {
  display: flex;
  flex-direction: column;
}
.LCD > div {
  font-family: "alarm clock";
  font-size: x-large;
}
</style>