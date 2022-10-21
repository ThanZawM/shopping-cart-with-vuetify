<template>
  <v-card class="card-style mx-auto" :width="wdth" style="position: relative">
    <div
      style="
        position: absolute;
        z-index: 1;
        margin-top: 16px;
        margin-left: 20px;
      "
    >
      <v-btn
        elevation="1"
        color="#423144"
        style="color: #ffffff"
        v-if="addtocart"
        >New</v-btn
      >
    </div>
    <v-img class="card-image" :width="wdth" :height="hgt" :src="items.image">
    </v-img>

    <v-card-text color="black" v-show="$route.path == '/'">
      <div class="itemname">{{ items.title }}</div>
      <div class="itemprice">${{ items.price }}</div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "Card",
  props: ["items", "addtocart", "wdth", "hgt"],
};
</script>

<style scoped>
.itemname {
  font-weight: bold;
}

.itemprice {
  font-weight: bold;
}

.card-style {
  box-shadow: none !important;
}
.card-image {
  border-radius: 20px;
}
</style>
