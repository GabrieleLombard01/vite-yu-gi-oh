<script>
import { store } from '../data/store';
import { types } from '../data/index';
import appSelect from './appSelect.vue';

export default {
    components: { appSelect },
    data() {
        return {
            store,
            types,
        };
    },
    methods: {
        onTypeChange(type) {
            this.$emit('type-change', type); // Emitiamo l'evento al componente padre (App.vue)
        },
    },
};
</script>

<template>
    <div class="d-flex justify-content-center align-items-center">
        <h1 class="text-center title_font mt-2">Pokedex</h1>
        <div class="filter">
            <appSelect class="rounded-2 ms-5" defaultLabel="All types" :options="types" @option-change="onTypeChange" />
        </div>
    </div>
</template>
  

  