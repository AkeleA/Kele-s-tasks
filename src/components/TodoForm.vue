<template>
  <div>
    <form @submit.prevent="addItemAndClear" action="">
      <input v-model="todo" type="text" />
      <button>Add</button>
    </form>
  </div>
</template>

<script lang="ts">
import { ref } from 'vue'
import { useTodoListStore } from '@/stores/useTodoListStore'

export default {
  setup() {
    const todo = ref('')
    const store = useTodoListStore()

    function addItemAndClear() {
      const userInput = todo.value.trim()

      if (userInput === '') {
        window.alert('Please type something before adding.')
      } else {
        store.addTodo(userInput)
        todo.value = ''
      }
    }

    return { todo, addItemAndClear }
  }
}
</script>

<style scoped>
form {
  margin-bottom: 1.5vh;
}

input {
  margin-top: 18px;
  margin-bottom: 25px;
  height: 3vh;
  width: 50%;
}

button {
  margin-left: 18px;
  background-color: #08b83c;
  padding: 5px 10px;
  border: none;
  border-radius: 4px;
  font-weight: 800;
  color: white;
  width: 15%;
}
</style>
