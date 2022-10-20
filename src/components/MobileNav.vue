<template>
    <v-app-bar
      color="#fbf4f9"
      class="black--text"
      dense
      dark
      v-if="!$vuetify.breakpoint.lgAndUp"
    >
      <v-app-bar-nav-icon
        color="black"
        @click="drawer = true"
      ></v-app-bar-nav-icon>

      <v-spacer></v-spacer>

      <v-toolbar-title>LOGO</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-navigation-drawer
        v-model="drawer"
        app
        temporary
        width="100%"
        class="white--text"
      >
        <v-list nav dense>
          <v-list-item-group
            v-model="group"
            active-class="green--text text--accent-4"
          >
            <v-list-item> Home </v-list-item>

            <v-list-item>
              <v-list-item-title>E-Commerce</v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>

      <v-btn class="black--text" icon @click="clickCart = true">
        <v-badge color="#423144" overlap content="3">
          <v-icon large>{{ svgPath }}</v-icon>
        </v-badge>
      </v-btn>
    </v-app-bar>
</template>

<script>
import { mdiCart } from "@mdi/js";
export default {
  data() {
    return {
      clickCart: false,
      svgPath: mdiCart,
      drawer: false,
    };
  },
};
</script>
