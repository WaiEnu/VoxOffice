<template>
  <div>
    <ul>
      <li v-for="item in food" v-bind:key=item>
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
const food = ["Pizza", "French fries", "Spaghetti"];
</script>
