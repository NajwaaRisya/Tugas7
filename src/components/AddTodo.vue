<template>
    <div class="add-todo">
      <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new task" />
      <button @click="addTodo">Add</button>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue';
  import { useTodoStore } from '../stores/todo';
  
  export default {
    setup() {
      const newTodo = ref('');
      const todoStore = useTodoStore();
  
      const addTodo = () => {
        if (newTodo.value.trim()) {
          todoStore.addTodo(newTodo.value);
          newTodo.value = '';
        }
      };
  
      return { newTodo, addTodo };
    },
  };
  </script>
  
  <style scoped>
  .add-todo {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  </style>
  