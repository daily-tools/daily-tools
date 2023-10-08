<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <div class="d-flex align-center">
        Daily Tools
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/daily-tools"
        target="_blank"
        text
      >
        <v-icon>mdi-github</v-icon>
        <span class="mr-2">Github</span>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  name: 'App',

  data: () => ({
    //
  }),
});
</script>
