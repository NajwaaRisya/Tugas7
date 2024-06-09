<template>
    <div class="todo-item" :class="{ completed: todo.completed }">
      <input type="checkbox" v-model="todo.completed" @change="toggleTodo" />
      <span>{{ todo.text }}</span>
      <button @click="removeTodo">Delete</button>
    </div>
  </template>
  
  <script>
  import { useTodoStore } from '../stores/todo';
  
  export default {
    props: ['todo', 'index'],
    setup(props) {
      const todoStore = useTodoStore();
  
      const toggleTodo = () => {
        todoStore.toggleTodo(props.index);
      };
  
      const removeTodo = () => {
        todoStore.removeTodo(props.index);
      };
  
      return { toggleTodo, removeTodo };
    },
  };
  </script>
  
  <style scoped>
  .todo-item {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  
  .todo-item.completed span {
    text-decoration: line-through;
  }
  </style>
  