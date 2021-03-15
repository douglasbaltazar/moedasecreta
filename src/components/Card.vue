<template>
  <v-card
    class="mx-auto mt-3"
    max-width="344"
  >
    <v-card-text>
      <div>{{ moeda.tag }}</div>
      <p class="display-1 text--primary">
        {{ moeda.nome }}
      </p>
      <p style="color: blue;"><strong>Maior do dia: {{ moeda.maior }} R$</strong> </p>
      <div class="text--primary">
        Menor foi <strong><span style="color: red;">{{ moeda.menor }} R$</span></strong><br>
        Volume {{ moeda.volume }} R$
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        text
        color="deep-purple accent-4"
      >
        Painel Mercado
      </v-btn>
      <span style="color: green"> Agora <strong>{{ moeda.atual }} R$</strong> </span>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
    props: {
        moeda: {
            type: Object,
            required: true
        },
    },
}
</script>

<style>
.stats {
    left: 0;
}

</style>