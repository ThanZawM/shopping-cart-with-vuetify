<template>
  <v-navigation-drawer
    app
    color="#fbf4f9"
    permanent
    left
    v-if="$vuetify.breakpoint.lgAndUp"
  >
    <v-card-subtitle>
      <h1><router-link to="/#">LOGO</router-link></h1>
    </v-card-subtitle>
    <v-divider width="50"></v-divider>
    <v-card-subtitle>
      <h2><div @click="scrollToContent('home')">Home</div></h2>
    </v-card-subtitle>
    <v-divider width="60"></v-divider>
    <v-card-subtitle>
      <!-- { path: '/Pulse/Definition',id:'Alignment'}" -->
      <h2>
        <div @click="scrollToContent('ecommerce')">E-Commerce</div>
      </h2>
    </v-card-subtitle>
    <v-divider width="150"></v-divider>
    <br /><br />
    <v-divider></v-divider>
    <v-container my-5 @click="clickCart = true">
      <v-badge color="#423144" overlap :content="testCartValue">
        <v-icon x-large>{{ svgPath }}</v-icon>
      </v-badge>
      <!-- <v-img
        style="margin: 15px auto"
        :src="require('@/assets/images/img1.jpg')"
        width="50"
      /> -->
    </v-container>

    <CardNav v-if="clickCart" :dialog="true"></CardNav>
  </v-navigation-drawer>
</template>

<script>
import CardNav from "@/components/CartNav.vue";
import { mdiCart } from "@mdi/js";
export default {
  data() {
    return {
      clickCart: false,
      svgPath: mdiCart,
      testCartValue: 3,
    };
  },
  methods: {
    scrollToContent(value) {
      window.scrollTo(
        0,
        document.getElementById(value).getBoundingClientRect().y +
          window.scrollY -
          120
      );
    },
  },
  components: {
    CardNav,
  },
};
</script>

<style scoped>
>>> .v-divider {
  margin: auto !important;
}
</style>
