<template>
  <div id="app">
    <NavBar />
    <router-view />
    <HFooter class="footie"></HFooter>
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import HFooter from "vue-hacktiv8-footer";
export default {
  components: {
    NavBar,
    HFooter,
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
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
.footie {
  margin-top: auto;
}
</style>
