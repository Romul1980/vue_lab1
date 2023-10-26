<script setup>

import TheCounter from "@/TheCounter.vue";
import {ref} from "vue";
const counters = ref(["Question 1", "Question 2", "Question 3", "Question 4"]);
const voites = ref(0);
const handleVoited = () => {
  voites.value++;
}
</script>
<template>
  <div class="counter_holder">
    <div class="counter__voited">{{voites}}</div>
    <div class="counter__items">
      <TheCounter v-for="title in counters" :title = "title" @voited="handleVoited"/>
    </div>


  </div>
</template>
<script>
export default {
  name: 'TheVoiting'
}
</script>
<style scoped>
.counter__items {
  padding: 10px;
  background: #181818;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  gap: 10px;
}
</style>