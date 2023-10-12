<script lang="ts">
import { useTodoListStore } from '@/stores/useTodoListStore'
import { storeToRefs } from 'pinia'
export default {
  setup() {
    const store = useTodoListStore()
    const { toggleCompleted, deleteTodo } = store
    // storeToRefs lets todoList keep reactivity:
    const { todoList } = storeToRefs(store)
    return { todoList, toggleCompleted, deleteTodo }
  }
}
</script>

<template>
  <div v-for="todo in todoList" :key="todo.id" class="todo-container">
    <div :class="{ completed: todo.completed }">{{ todo.item }}</div>
    <span @click.stop="toggleCompleted(todo.id)">&#10004;</span>
    <span @click="deleteTodo(todo.id)">&#10060;</span>
  </div>
</template>

<style scoped>
span {
  margin: 0 10px;
  cursor: pointer;
}

.completed {
  text-decoration: line-through;
}

.list {
  display: flex;
  justify-content: center;
}
.todo-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 80%;
  padding: 10px;
  margin: 20px 0;
  background-color: #f2f2f2;
  border: 1px solid #ddd;
  border-radius: 5px;
}

.item {
  display: flex;
  font-size: 1.5em;
  justify-content: space-between;
  width: 80vw;
  padding: 5px;
}
</style>
