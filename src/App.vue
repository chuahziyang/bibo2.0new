<template>
  <v-app>
    <v-main>
      <LoginPage />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import LoginPage from "./components/LoginPage.vue";

export default Vue.extend({
  name: "App",

  components: {
    LoginPage,
  },

  data: () => ({
    //
  }),
});
</script>
