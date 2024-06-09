<template>
  <div id="app">
    <h1>Todo List</h1>
    <todo-list />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoList,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #f0f8ff;
  padding: 20px;
  border-radius: 10px;
}

h1 {
  color: #3498db;
}
</style>
