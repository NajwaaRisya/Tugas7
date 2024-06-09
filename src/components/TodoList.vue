<template>
    <div class="todo-list">
      <add-todo />
      <div v-for="(todo, index) in todos" :key="index">
        <todo-item :todo="todo" :index="index" />
      </div>
      <p>Total incomplete tasks: {{ incompleteTodos }}</p>
    </div>
  </template>
  
  <script>
  import { useTodoStore } from '../stores/todo';
  import AddTodo from './AddTodo.vue';
  import TodoItem from './TodoItem.vue';
  
  export default {
    components: {
      AddTodo,
      TodoItem,
    },
    setup() {
      const todoStore = useTodoStore();
      return {
        todos: todoStore.todos,
        incompleteTodos: todoStore.incompleteTodos,
      };
    },
  };
  </script>
  
  <style scoped>
  .todo-list {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    background-color: #f9f9f9;
    border-radius: 10px;
  }
  </style>
  