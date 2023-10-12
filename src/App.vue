<script setup lang="ts">
import { defineProps } from 'vue'
import TodoApp from './components/TodoApp.vue'

const props = defineProps({})
</script>

<template>
  <div class="top-app">
    <todo-app />
  </div>
</template>

<style scoped>
.top-app {
  background-color: #5baff5;
  padding: 2vh;
  display: flex;
  flex-direction: column;
  justify-content: center; /* Center vertically */
  align-items: center; /* Center horizontally */
  min-height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

/* Media query for smaller phone screens */
@media (max-width: 767px) {
  #app {
    width: 100%; /* Adjust the width for smaller phone screens */
  }
}

/* Media query for larger phone screens */
@media (min-width: 768px) and (max-width: 1023px) {
  #app {
    width: 90%; /* Adjust the width for larger phone screens */
  }
}

/* Media query for larger screens (tablets and up) */
@media (min-width: 1024px) {
  #app {
    width: 40%; /* Default width for larger screens */
  }
}
</style>
