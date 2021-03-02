<template>
  <v-app id="landing-page">
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        <h1 class="header">Todo App</h1>
      </div>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main>
      <div id="container">
        <todo-list/>
      </div>
      

    </v-main>
  </v-app>
</template>

<script>
import TodoList from './components/TodoList.vue';

export default {
  name: 'App',

  components: {
    TodoList,
  },

  data: () => ({
    //
  }),
};
</script>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
}

#landing-page {
  background-image: linear-gradient(to bottom right, rgb(151, 206, 79), rgb(39, 255, 208));
  height: 100%;
}

#container {
  display: flex;
  justify-content: center;
  margin: 0 auto;
  max-width: 600px;
}


.header {
  font-size: 30px;
  color: rgb(255, 255, 255);
}
</style>