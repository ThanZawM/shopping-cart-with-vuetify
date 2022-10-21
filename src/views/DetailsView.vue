<template>
  <div>
    <v-container style="height: 90vh">
      <v-row>
        <v-col cols="8" class="detials">
          <v-row>
            <v-col>
              <v-container style="text-align: start">
                <router-link to="/">Home</router-link> /
                <router-link to="/">E-commerce</router-link> /
                {{ items[$route.params.id].title }}</v-container
              >
            </v-col>
          </v-row>

          <v-row>
            <v-col>
              <v-container>
                <h1>{{ items[$route.params.id].title }}</h1>
                <hr class="subTitle-hr" />
              </v-container>
            </v-col>
          </v-row>

          <v-row
            ><v-col cols="4">
              <v-container>
                <Card
                  :items="items[$route.params.id]"
                  :addtocart="true"
                  :wdth="230"
                  :hgt="300"
                ></Card>
                <!-- <h1>{{$route.params}}</h1> -->
              </v-container>
            </v-col>
            <v-col cols="8">
              <v-container>
                <v-container>
                  <p style="text-align: left">
                    {{ items[$route.params.id].description }}
                  </p>
                </v-container>
                <v-divider></v-divider>
                <v-container my-6>
                  <h1 style="text-align: left">
                    ${{ items[$route.params.id].price }}
                  </h1>
                  <h3 style="text-align: left; margin-top: 5px">
                    Shipping: {{ items[$route.params.id].shipping }}
                  </h3>
                </v-container>
                <v-divider></v-divider>
                <v-container mt-6>
                  <v-col cols="7">
                    <v-row align="center" justify="space-between" no-gutters>
                      <v-btn-toggle>
                        <v-btn icon
                          ><v-icon color="green">{{ this.mdiPlus }}</v-icon>
                        </v-btn>
                        <input
                          type="number"
                          value="1"
                          style="
                            width: 65px;
                            text-align: center;
                            display: inline-block;
                            border: none;
                          "
                        />
                        <v-btn icon
                          ><v-icon color="green">{{
                            this.mdiMinus
                          }}</v-icon></v-btn
                        >
                      </v-btn-toggle>

                      <v-btn
                        color="#423144"
                        class="white--text py-6 px-8"
                        @click="storeData($route.params.id)"
                        >ADD TO CART
                      </v-btn>

                      <CardNav
                        v-if="clickCart"
                        :dialog="clickCart"
                        :productid="$route.params.id"
                      ></CardNav>
                    </v-row>
                  </v-col>
                </v-container>
              </v-container>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>

    <Footer></Footer>
  </div>
</template>

<script>
import Footer from "@/components/Footer.vue";
import Card from "@/components/Card.vue";
import CardNav from "@/components/CartNav.vue";
import { mdiPlus, mdiMinus } from "@mdi/js";

export default {
  components: { Footer, Card, CardNav },
  data() {
    return {
      clickCart: false,
      mdiPlus: mdiPlus,
      mdiMinus: mdiMinus,
      cartItems: [],
      items: [
        {
          id: 1,
          title: "Blue Pants",
          description:
            "These blue pants for men stand out as fashionable attire that any man would be proud to wear.",
          price: 79,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c1791a0313a1.jpg",
          shipping: "Free Shipping",
        },
        {
          id: 2,
          title: "Brown Jacket",
          description:
            "This brown jacket for men looks great and is good for all occasions.",
          price: 159,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178fc9abfbb.jpg",
          shipping: "Free Shipping",
        },
        {
          id: 3,
          title: "Green Bag",
          description:
            "A fashionable green bag that lets you carry around what you need while looking stylish.",
          price: 89,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178e836f01a.jpg",
          shipping: "Free Shipping",
        },
        {
          id: 4,
          title: "Turquoise Dress",
          description:
            "A lovely turquoise dress to look fabulous in while enjoying a night on the town.",
          price: 120,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178d6d607e7.jpg",
          shipping: "Free Shipping",
        },
      ],
    };
  },
  methods: {
    storeData(id) {
      console.log(id);
      let oldData = JSON.parse(localStorage.getItem("cartItems"));
      this.cartItems = [this.items[id]];
      if (oldData === null) {
        localStorage.setItem("cartItems", JSON.stringify(this.cartItems));
      } else {
        oldData = [...oldData, ...this.cartItems];
        localStorage.setItem("cartItems", JSON.stringify(oldData));
      }

      this.clickCart = !this.clickCart;
    },
  },
};
</script>

<style scoped>
.subTitle-hr {
  margin: 20px auto;
  max-width: 50px;
  border-color: #423144;
  border-width: 2px;
}
.detials {
  margin: auto;
}
</style>
