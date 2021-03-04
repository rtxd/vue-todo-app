<template>
  <v-app id="landing-page">
    <v-app-bar
      app
      absolute
      color="pimary"
      prominent
      dark
      shrink-on-scroll
      fade-img-on-scroll
      scroll-target="#scrolling-techniques-3"
    >
      <div class="d-flex align-center" id="header-container">
        <h1 class="header">Todo List</h1>
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
  /* background-image: linear-gradient(to bottom right, rgb(151, 206, 79), rgb(39, 255, 208)); */
  background-image: url("https://natureconservancy-h.assetsadobe.com/is/image/content/dam/tnc/nature/en/photos/tnc_69881045.jpg?crop=240,0,2400,1320&wid=4000&hei=2200&scl=0.6") ;
  background-size: 200vh;
  min-height: 100vh;
}
  
#container {
  display: flex;
  justify-content: center;
  margin: 0 auto;
  max-width: 80vw;
}


.header {
  font-size: 30px;
  color: rgb(255, 255, 255);
  display: flex;
  justify-content: center;
}
</style>