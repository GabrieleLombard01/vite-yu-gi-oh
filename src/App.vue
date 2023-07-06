<script>
import axios from 'axios';
import { store } from '../src/data/store';
import appMain from '../src/components/appMain.vue';
import appHeader from '../src/components/appHeader.vue';

export default {
  components: { appMain, appHeader },

  created() {
    store.isLoading = true;
    this.fetchPokemons(); // Chiamiamo il metodo per ottenere i Pokemon all'avvio dell'app
  },

  methods: {
    fetchPokemons() {
      // Costruiamo l'endpoint aggiungendo il filtro del tipo se presente
      let endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
      if (store.selectedType) {
        endpoint += `?eq[type1]=${store.selectedType}`;
      }

      axios
        .get(endpoint)
        .then((res) => {
          store.pokemon = res.data.docs;
        })
        .catch((err) => {
          console.error(err.message);
        })
        .finally(() => {
          store.isLoading = false;
        });
    },

    onTypeChange(type) {
      store.selectedType = type; // Aggiorniamo il tipo selezionato nello store
      this.fetchPokemons(); // Richiamiamo il metodo per ottenere i Pokemon con il nuovo filtro
    },
  },
};
</script>

<template>
  <div>
    <!-- HEADER: -->
    <header>
      <appHeader @type-change="onTypeChange" />
    </header>

    <!-- MAIN CONTENT: -->
    <main>
      <appMain />
    </main>
  </div>
</template>


<style lang="scss">
@use '../src/assets/scss/style.scss';
</style>


