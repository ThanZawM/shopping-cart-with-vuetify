<template>
  <div class="main-container">
    <v-row class="home-container">
      <v-container>
        <h1 class="main-title">Clothing & Fashion</h1>
        <h2 class="sub-title">A Ladies Clothing Store Boutique</h2>
        <v-row>
          <v-spacer />
          <v-img
            width="500"
            src="https://static.s123-cdn-static-d.com/ready_uploads/svg/normal_60472d64ed4c4.svg"
            class="my-12"
          ></v-img>
          <v-spacer />
        </v-row>
      </v-container>
    </v-row>

    <v-row>
      <v-spacer />
      <v-col
        v-for="(item, index) in items"
        :key="index"
        cols="12"
        sm="6"
        md="4"
        lg="3"
      >
        <Card :items="item"></Card>
      </v-col>
      <v-spacer />
    </v-row>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from "@/components/Card.vue";

export default {
  name: "HomeView",
  data() {
    return {
      items: [
        {
          title: "Blue Pants",
          price: 79,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c1791a0313a1.jpg",
        },
        {
          title: "Brown Jacket",
          price: 159,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178fc9abfbb.jpg",
        },
        {
          title: "Green Bag",
          price: 89,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178e836f01a.jpg",
        },
        {
          title: "Turquoise Dress",
          price: 120,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178d6d607e7.jpg",
        },
      ],
    };
  },
  components: {
    Card,
  },
};
</script>

<style scoped>
.card-container {
  margin: auto;
  display: flex;
}
.home-container {
  background: #f6e5f5;
  width: "100vh";
  margin: auto;
}
.main-title {
  margin-top: 150px;
  font-weight: bolder;
  font-size: 4em;
}
.sub-title {
  margin-top: 20px;
  /* font-weight: bold; */
  font-size: 2em;
}
.img-container {
  margin: auto;
}
</style>
