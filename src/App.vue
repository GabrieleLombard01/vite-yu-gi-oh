<script >
import appMain from '../src/components/appMain.vue'
export default {
  components: { appMain }
};
</script>

<template>
  <!--HEADER:-->
  <HEADER>
    <h1 class="text-center title_font mt-2">Pokedex</h1>
  </HEADER>

  <!--MAIN CONTENT:-->
  <main>
    <appMain />
  </main>
</template>

<style lang="scss">
@use '../src/assets/scss/style.scss';
</style>
