<script>
import { ref } from 'vue'
export default {
  name: 'Cards',
  setup(){
    const max = 8;
    let card = ref(0);
    card.value = Math.floor(Math.random() * max);
		const shuffle = () => (card.value = Math.floor(Math.random() * max));

    const emoji = ["😀", "😘", "😢", "🤮","😬","😍","🤔","😈"];
    return{
      card,
      shuffle,
      emoji
    }

  }

}
</script>

<template>
  <div class="container">
    <div class="LCD">
      <div>{{ emoji[card] }}</div>
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