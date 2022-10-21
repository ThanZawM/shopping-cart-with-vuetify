<template>
  <div>
    <v-dialog v-model="dialog" width="500">
      <v-card>
        <v-card-title
          style="background: #423144"
          class="text-h5 white--text py-5"
        >
          Your Cart
          <v-spacer></v-spacer>
          <v-btn icon @click="dialog = false">
            <v-icon dark color="black" class="white--text">{{
              this.mdiClose
            }}</v-icon>
          </v-btn>
        </v-card-title>

        <!-- <v-container v-for="(item, index) in items" :key="index">
          <Card :items="item" :wdth="200" :hgt="100"></Card>
        </v-container> -->

        <v-container>
          <v-card>
            <v-container v-for="(obj, index) in cartObjs" :key="index">
              <v-img :src="obj.image"></v-img>
              <v-card-text>{{ obj.title }}</v-card-text>
              <v-card-text>${{ obj.price }}</v-card-text>
            </v-container>
            <!-- <v-container>
              <v-card-tex> </v-card-tex>
            </v-container>
            <v-card-actions> </v-card-actions> -->
          </v-card>
        </v-container>

        <v-divider></v-divider>

        <v-card-actions>
          <v-spacer></v-spacer>
          <v-row no-gutters>
            <v-row>
              <v-col cols="6">
                <v-card-text>Total: </v-card-text>
              </v-col>

              <v-col cols="6">
                <v-card-text>EMPTY CART</v-card-text>
              </v-col>
            </v-row>
            <v-row>
              <v-col>
                <v-btn
                  color="#423144"
                  width="100%"
                  class="white--text"
                  @click="dialog = false"
                  >MAKE AN ORDER</v-btn
                >
                <v-btn
                  color="#423144"
                  class="my-3"
                  outlined
                  width="100%"
                  @click="dialog = false"
                  >CONTINUE SHOPPING</v-btn
                >
              </v-col>
            </v-row>
          </v-row>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script>
import { mdiClose, mdiPlus, mdiMinus } from "@mdi/js";
import Card from "./Card.vue";

export default {
  data() {
    return {
      mdiPlus: mdiPlus,
      mdiMinus: mdiMinus,
      mdiClose: mdiClose,
      cartObjs: [],
    };
  },
  props: { dialog: Boolean },
  components: { Card },
  created() {
    this.cartObjs = JSON.parse(localStorage.getItem("cartItems"));
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
  overflow: auto;
}
>>> .v-card {
  top: 0;
  height: 100%;
  overflow: auto;
}
</style>
