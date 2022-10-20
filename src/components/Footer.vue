<template>
  <v-footer bottom dark padless>
    <v-card flat tile color="#ffdbc5" class="text-center" width="100%">
      <v-card-text class="black--text pt-10"> Home | E-Commerce </v-card-text>

      <v-card-text class="black--text pt-3">
        Copyright © {{ new Date().getFullYear() }} All rights reserved - LOGO
      </v-card-text>

      <v-card-text class="black--text pt-0">
        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {};
</script>
