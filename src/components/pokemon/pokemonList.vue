<script >
import pokemonCard from './pokemonCard.vue';
import { store } from '../../data/store'
export default {
    components: { pokemonCard },
    data() {
        return { store }
    }
};
</script>

<template>
    <section id="pokemon">

        <div class="row g-2 row-cols-2 row-cols-md-3 row-cols-lg-4">
            <div v-for="pkm in store.pokemon" :key="pkm._id" class="col">
                <pokemonCard :name="pkm.name" :image="pkm.imageUrl" :type="pkm.type1" :number="pkm.number" />
            </div>
        </div>

    </section>
</template>

