<template>
  <v-app>
    <v-app-bar
      app
      color="darkgrey"
      dark
    >
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://i.pinimg.com/originals/62/d1/26/62d126dcfc3c38c276627e6a251a6c25.jpg"
          transition="scale-transition"
          width="40"
        />
        <span>Moeda Secreta</span>
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://www.mercadobitcoin.com.br/plataforma/dashboard/"
        target="_blank"
        text
      >
        <span class="mr-2">Mercado Bitcoin</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <MoedaSecreta/>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from 'vue';
import MoedaSecreta from './components/MoedaSecreta.vue';

export default Vue.extend({
  name: 'App',

  components: {
    MoedaSecreta,
  },

  data: () => ({
    //
  }),
});
</script>
