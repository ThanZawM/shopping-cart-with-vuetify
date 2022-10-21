<template>
  <div class="main-container">
    <v-row class="home-container" id="home">
      <v-container>
        <h1 class="main-title">Clothing & Fashion</h1>
        <h2 class="sub-title">A Ladies Clothing Store Boutique</h2>
        <v-row>
          <v-spacer />
          <v-img
            width="400"
            :src="require('@/assets/images/home.svg')"
            class="my-12"
          ></v-img>
          <v-spacer />
        </v-row>
      </v-container>
    </v-row>

    <v-container id="ecommerce">
      <h1 class="sub-title">NEW ARRIVAL</h1>
      <hr />
      <v-row>
        <v-spacer />
        <v-col
          v-for="item in items"
          :key="item.id"
          cols="12"
          sm="6"
          md="3"
          lg="3"
          xl="3"
        >
          <v-container my-12>
            <router-link
              :to="{ name: 'details', params: { id: items.indexOf(item) } }"
              ><Card
                :items="item"
                :addtocart="true"
                :wdth="230"
                :hgt="300"
              ></Card
            ></router-link>
            <!-- <router-link to="/details/:"
              ><Card
                :items="item"
                :addtocart="true"
                :wdth="230"
                :hgt="300"
              ></Card
            ></router-link> -->
          </v-container>
        </v-col>
        <v-spacer />
      </v-row>
    </v-container>

    <Footer></Footer>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from "@/components/Card.vue";
import Footer from "@/components/Footer.vue";

export default {
  name: "HomeView",
  mounted() {
    window.scrollTo(0, 0);
  },
  data() {
    return {
      items: [
        {
          id: 1,
          title: "Blue Pants",
          description:
            "These blue pants for men stand out as fashionable attire that any man would be proud to wear.",
          price: 79,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c1791a0313a1.jpg",
          // image: "@/assets/images/blue-pants.webp"
        },
        {
          id: 2,
          title: "Brown Jacket",
          description:
            "This brown jacket for men looks great and is good for all occasions.",
          price: 159,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178fc9abfbb.jpg",
        },
        {
          id: 3,
          title: "Green Bag",
          description:
            "A fashionable green bag that lets you carry around what you need while looking stylish.",
          price: 89,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178e836f01a.jpg",
        },
        {
          id: 4,
          title: "Turquoise Dress",
          description:
            "A lovely turquoise dress to look fabulous in while enjoying a night on the town.",
          price: 120,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178d6d607e7.jpg",
        },
      ],
    };
  },
  components: {
    Card,
    Footer,
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
  margin-top: 100px;
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
hr {
  margin: 20px auto;
  max-width: 50px;
  border-color: #423144;
  border-width: 2px;
}
</style>
