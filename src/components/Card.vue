<template>
  <v-card
    class="card-style mx-auto my-12"
    width="256"
    style="position: relative"
  >
    <div style="position: absolute; z-index: 1; margin-top: 16px; margin-left: 20px;">
      <v-btn elevation="1" color="#423144" style="color: #ffffff;">New</v-btn>
    </div>
    <v-img class="card-image" width="280" height="300" :src="items.image">
    </v-img>

    <v-card-text color="black">
      <div class="itemname">{{ items.title }}</div>
      <div class="itemprice">${{ items.price }}</div>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "Card",
  props: ["items"],
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
