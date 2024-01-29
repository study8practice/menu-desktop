<template>
  <div>
    <MainMenuSaraiva :n1menu="menu"  />
  </div>
</template>

<script>
import MainMenuSaraiva from './components/saraiva/MainMenuSaraiva.vue'
import menujson from './api/saraiva.json';

export default {
  name: 'App',
  components: {
    MainMenuSaraiva
  },
  computed: {
    menu(){
      return menujson.menu;
    },
  },
  created(){
    console.log(typeof this.menu)
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
body {
  background: #fff;
  margin: 0;
}
</style>
