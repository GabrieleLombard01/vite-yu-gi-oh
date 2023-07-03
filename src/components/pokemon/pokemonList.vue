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
            console.log(res.data)
        });
    }
};
</script>

<template>
    <section id="pokemon">

    </section>
</template>

<style scoped></style>