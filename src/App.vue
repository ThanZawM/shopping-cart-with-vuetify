<template>
  <div id="app">
    <v-app>
      <Nav />
      <MobileNav />
      <v-main>
        <router-view />
      </v-main>
    </v-app>
  </div>
</template>

<script>
import Nav from "@/components/Navigation.vue";
import MobileNav from "./components/MobileNav.vue";

export default {
  components: {
    Nav,
    MobileNav,
    
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
</style>
