<script >
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=Electric&sort[number]=desc';

import appMain from '../src/components/appMain.vue'
export default {
  components: { appMain },
  data() {
    return {
      pokemon: []
    }
  },
  created() {
    axios.get(endpoint).then(res => {
      this.pokemon = res.data.docs;
    });
  }
};
</script>

<template>
  <!--HEADER:-->
  <HEADER>
    <h1 class="text-center title_font mt-2">Pokedex</h1>
  </HEADER>

  <!--MAIN CONTENT:-->
  <main>
    <appMain :pokemon="pokemon" />
  </main>
</template>

<style lang="scss">
@use '../src/assets/scss/style.scss';
</style>
