<template>
  <div class="app-container">
    <h1>Todo List</h1>
    <todo-form />
    <todo-list />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import TodoForm from './TodoForm.vue'
import TodoList from './TodoList.vue'
export default defineComponent({
  components: { TodoForm, TodoList },
  setup() {
    return {}
  }
})
</script>

<style scoped>
h1 {
  color: white;
  font-size: 24px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  text-transform: uppercase;
}
.app-container {
  padding: 3vh;
  min-height: 100vh;
  width: 40vw;
  background-color: rgb(76, 76, 153);
}

/* Responsive CSS using media queries */
@media (max-width: 768px) {
  .app-container {
    padding: 2rem; /* Decrease padding for smaller screens */
    max-width: 100%; /* Full-width container for small screens */
  }
}

/* Additional media query for phone screens */
@media (max-width: 480px) {
  .app-container {
    padding: 1rem; /* Further decrease padding for phone screens */
  }
}

/* Additional media query for larger phone screens */
@media (max-width: 640px) {
  .app-container {
    padding: 1.5rem; /* Adjust padding for larger phone screens */
  }
}
</style>
