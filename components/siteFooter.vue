<template>
  <v-footer
    :class="
      $vuetify.theme.dark
        ? 'blue-grey darken-4 grey--text text--lighten-1'
        : 'grey lighten-3 grey--text text--darken-4'
    "
    class="site-footer"
  >
    <v-container>
      <v-divider class="mb-5"></v-divider>
      <v-row>
        <v-col cols="12" md="7">
          <div
            class="d-flex flex-wrap justify-md-start justify-center justify-md-none"
          >
            <nuxt-link to="/">Главная</nuxt-link>
          </div>
        </v-col>
        <v-col class="text--secondary text-center text-md-right">
          {{ new Date().getFullYear() }} ©
          <nuxt-link class="primary--text" to="/">Кузнецов Максим</nuxt-link>
        </v-col>
      </v-row>
    </v-container>
  </v-footer>
</template>

<script>
export default {}
</script>

<style>
.site-footer a {
  text-decoration: none;
}
</style>
