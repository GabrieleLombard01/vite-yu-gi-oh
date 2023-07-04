<script >
export default {
    props: {
        name: String,
        image: String,
        type: String,
        number: String
    }
};
</script>

<template>
    <div class="poke-card">
        <img :src="image" :alt="name" class="img-fluid">
        <h4>{{ name }}</h4>
        <div class="poke-type">{{ type }}</div>
        <div class="poke-number">{{ number }}</div>
    </div>
</template>

<style></style>