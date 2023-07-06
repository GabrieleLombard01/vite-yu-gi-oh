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

    <div class="style_pokedex">
      <div class="center_div">
        <div class="speaker_poked d-inline-block"></div>
        <div class="front_camera d-inline-block text-white"></div>
      </div>
      <main>

        <appMain />
      </main>
      <div class="d-flex">
        <button class="home_btn"></button>
      </div>
    </div>
  </div>
</template>


<style lang="scss">
@use '../src/assets/scss/style.scss';

/*STYLE POKEDEX:*/
.style_pokedex {
  background-color: rgb(72, 72, 72);
  width: 580px;
  margin: 0 auto 50px auto;
  padding-top: 20px;
  border-radius: 50px;
}

.center_div {
  width: 315px;
  margin: auto;
}

.speaker_poked {
  background-color: black;
  height: 8px;
  margin: 7px auto;
  width: 250px;
  border-radius: 5px;
}

.front_camera {
  height: 25px;
  width: 25px;
  background-color: black;
  margin: 0px 20px;
  border-radius: 50%;

}

.home_btn {
  background-color: grey;
  border: solid black;
  margin: 20px auto;
  height: 80px;
  width: 80px;
  border-radius: 50%;
}

.home_btn:hover {
  background-color: black;
}
</style>


