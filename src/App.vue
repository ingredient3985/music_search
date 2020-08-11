<template>
  <v-app>
    <v-app-bar
      app
      color="blue"
      dark
    >
    <v-toolbar-title class="headline text-uppercase">
      <router-link to="/" style="color:white;text-decoration:none;"><span>Alubm Searcher</span></router-link>
    </v-toolbar-title>

      <!-- <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        /> -->

        <!-- <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        /> -->

      <v-spacer></v-spacer>

      <v-btn
        text
        to="/"
      >
        <span class="mr-2">home</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',


  data: () => ({
    //
  }),
};
</script>
