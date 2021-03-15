<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          src="https://discord.com/assets/41484d92c876f76b20c7f746221e8151.svg"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          Bem vindo a Moeda Secreta
        </h1>

        <p class="subheading font-weight-regular">
          Hoje 11:40 da manhã em um Domingo, dia 14 de março de 2021,
          <br>um dev tava sem o que fazer.
        </p>
      </v-col>
      <v-col
        class="mb-5"
        cols="12"
      >
      <template v-for="moeda in moedas">
        <Card :moeda="moeda" :key="moeda.tag" />
      </template>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
  import Vue from 'vue'
  import axios from 'axios'
  import Card from './Card.vue'

  export default Vue.extend({
    name: 'MoedaSecreta',

    data: () => ({
      moedas: [],

    }),
    components: {
      Card,
    },
    mounted() {
        this.getCHZ()
        this.getWBX()
        console.log(this.moedas)
    },
    methods: {
        getCHZ() {
            axios
                .get('http://localhost:8080/api/CHZ/ticker')
                .then(response => { 
                  const moeda = {
                    nome: 'Chiliz',
                    tag: 'CHZ',
                    maior: response.data.ticker.high,
                    menor: response.data.ticker.low,
                    abriu: response.data.ticker.open,
                    atual: response.data.ticker.last,
                    volume: response.data.ticker.vol,
                    link: 'https://www.mercadobitcoin.com.br/plataforma/negociar/crypto/chz'
                  }
                  this.moedas.push(moeda)
                })
                .catch(e => console.log(e))
        },
        getWBX() {
            axios
                .get('http://localhost:8080/api/WBX/ticker')
                .then(response => { 
                  const moeda = {
                    nome: 'WiBX',
                    tag: 'WBX',
                    maior: response.data.ticker.high,
                    menor: response.data.ticker.low,
                    abriu: response.data.ticker.open,
                    atual: response.data.ticker.last,
                    volume: response.data.ticker.vol,
                    link: 'https://www.mercadobitcoin.com.br/plataforma/negociar/crypto/wbx'
                  }
                  this.moedas.push(moeda)
                })
                .catch(e => console.log(e))
        }
    }
  })
</script>
