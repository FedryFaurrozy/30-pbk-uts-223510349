<template>
  <div class="app">
    <h1>Aplikasi To-Do List</h1>
    <todo-list />
  </div>
</template>

<script>
import TodoList from "./TodoList.vue";

export default {
  components: {
    TodoList,
  },
};
</script>

<style scoped>
.app {
  text-align: center;
  font-family: sans-serif;
}
</style>
