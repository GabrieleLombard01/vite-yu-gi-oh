<script >
import pokemon from '../components/pokemon/pokemonList.vue'
export default {
    components: { pokemon },
    props: { pokemon: Array }
};
</script>

<template>
    <!--POKEMON LIST:-->
    <pokemon :pokemon="pokemon" />
</template>

<style scoped></style>