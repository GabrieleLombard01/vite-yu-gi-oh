<script >
import axios from 'axios';
const endpoint = 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?eq[type1]=Electric&sort[number]=desc';
export default {
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
    <section id="pokemon">
        <ul>
            <li v-for="pkm in pokemon" :key="pkm._id">{{ pkm.name }}</li>
        </ul>
    </section>
</template>

<style scoped></style>