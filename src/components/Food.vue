<template>
  <li>
    <ul>
      <li v-for="item in food" v-bind:key=item>
        {{ item }}
      </li>
    </ul>
  </li>
</template>

<script setup lang="ts">
const food = ["Pizza", "French fries", "Spaghetti"];
</script>
