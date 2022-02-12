<template>
  <div id="app">
    <h2>To-do list</h2>
    <TodoList />

  </div>
</template>

<script>
import TodoList from './components/TodoList'

export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
