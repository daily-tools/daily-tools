<template>
  <v-container>
    <v-card outlined href="/password-generator">
      <v-card-title>Password Generator</v-card-title>
      <v-card-subtitle>Generate a secure password</v-card-subtitle>
      <v-card-text>
        Use our online password generator to instantly create a secure, random password.
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    name: 'Home',

    components: {
    },
  })
</script>
