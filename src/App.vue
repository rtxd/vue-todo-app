<template>
  <div id="app" class="container">
    <h1 class="header">Todo App</h1>
    <todo-list />
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
* {
  box-sizing: border-box;
}

html {
  background-image: linear-gradient(to bottom right, rgb(151, 206, 79), rgb(39, 255, 208));
  height: 100%;
}

.container {
  max-width: 600px;
  margin: 0 auto;
  
}

.header {
  font-size: 30px;
  color: rgb(255, 255, 255);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  
  
}
</style>
