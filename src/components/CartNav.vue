<template>
  <div>
    <v-dialog v-model="dialog" width="500">
      <v-card>
        <v-card-title class="text-h5 grey lighten-2">
          Your Cart
          <v-spacer></v-spacer>
          <v-icon dark color="black">{{ this.mdiClose }}</v-icon>
        </v-card-title>

        <v-card-text>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi ut
          aliquip ex ea commodo consequat. Duis aute irure dolor in
          reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
          pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
          culpa qui officia deserunt mollit anim id est laborum.
        </v-card-text>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="primary" text @click="dialog = false"> I accept </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
import { mdiClose } from "@mdi/js";

export default {
  data() {
    return {
      dialog: true,
      mdiClose: mdiClose,
    };
  },
};
</script>

<style scoped>
>>> .v-dialog {
  margin: 0;
  position: absolute;
  top: 0;
  right: 0;
  width: 50px;
  height: 100%;
  max-height: 100% !important;
}
>>> .v-card {
  height: 100%;
  top: 0;
}
</style>
