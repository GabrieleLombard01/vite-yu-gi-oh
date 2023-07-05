<script >
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons';
import { store } from '../src/data/store';
import appMain from '../src/components/appMain.vue';
import appHeader from '../src/components/appHeader.vue';

export default {
  components: { appMain, appHeader },

  created() {
    store.isLoading = true;
    axios.get(endpoint).then(res => {
      store.pokemon = res.data.docs;
    }).catch(err => {
      console.error(err.message);
    }).then(() => {
      store.isLoading = false;
    })
  }
};
</script>

<template>
  <!--HEADER:-->
  <HEADER>
    <appHeader />
  </HEADER>

  <!--MAIN CONTENT:-->
  <main>
    <appMain />
  </main>
</template>

<style lang="scss">
@use '../src/assets/scss/style.scss';
</style>
