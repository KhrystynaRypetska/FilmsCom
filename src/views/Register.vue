<template>
  <v-container class="fill-height">
    <v-row class="text-center d-flex justify-center">
      <v-col cols="12" md="6" lg="4" class="pa-5">
        <h1 class="ma-auto">Sing Up</h1>
        <p class="ma-auto">
          <router-link :to="{ name: 'login' }"> Need an account? </router-link>
        </p>
        <v-form @submit.prevent="onSubmit">
          <v-text-field label="Name" required></v-text-field>
          <v-text-field label="E-mail" required></v-text-field>
          <v-text-field label="Password" required></v-text-field>
          <v-btn
            class="mr-4"
            @click="onSubmit"
            color="primary"
            :disabled="isSubmitting"
          >
            Submit
          </v-btn>
        </v-form>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "FcRegister",
  computed: {
    isSubmitting() {
      return this.$store.state.auth.isSubmitting;
    },
  },
  methods: {
    onSubmit() {
      console.log("submit");
      this.$store.dispatch("register");
    },
  },
};
</script>
