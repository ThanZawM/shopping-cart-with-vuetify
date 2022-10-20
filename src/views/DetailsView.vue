<template>
  <div>
    <v-container style="height: 90vh">
      <v-row>
        <v-col cols="8" class="detials">
          <v-row>
            <v-col>
              <v-container style="text-align: start">
                <router-link to="/">Home</router-link> / E-commerce / Turquoise
                Dress</v-container
              >
            </v-col>
          </v-row>

          <v-row>
            <v-col>
              <v-container>
                <h1>TURQUOISE DRESS</h1>
                <hr class="subTitle-hr" />
              </v-container>
            </v-col>
          </v-row>

          <v-row
            ><v-col cols="4">
              <v-container>
                <Card :items="items[3]"></Card>
              </v-container>
            </v-col>
            <v-col cols="8">
              <v-container>
                <v-container>
                  <p style="text-align: left">{{ items[3].description }}</p>
                </v-container>
                <v-divider></v-divider>
                <v-container my-6>
                  <h1 style="text-align: left">${{ items[3].price }}</h1>
                  <h3 style="text-align: left; margin-top: 5px">
                    Shipping: {{ items[3].shipping }}
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

                      <v-btn color="#423144" class="white--text py-6 px-8"
                        >ADD TO CART</v-btn
                      >
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
import { mdiPlus, mdiMinus } from "@mdi/js";

export default {
  components: { Footer, Card },
  data() {
    return {
      mdiPlus: mdiPlus,
      mdiMinus: mdiMinus,
      items: [
        {
          title: "Blue Pants",
          description:
            "These blue pants for men stand out as fashionable attire that any man would be proud to wear.",
          price: 79,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c1791a0313a1.jpg",
          shipping: "Free Shipping",
        },
        {
          title: "Brown Jacket",
          description:
            "This brown jacket for men looks great and is good for all occasions.",
          price: 159,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178fc9abfbb.jpg",
          shipping: "Free Shipping",
        },
        {
          title: "Green Bag",
          description:
            "A fashionable green bag that lets you carry around what you need while looking stylish.",
          price: 89,
          image:
            "https://static1.s123-cdn-static-a.com/uploads/2031/2000_5c178e836f01a.jpg",
          shipping: "Free Shipping",
        },
        {
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
