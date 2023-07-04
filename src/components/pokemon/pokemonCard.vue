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
    <div class="card h-100">
        <img :src="image" :alt="name" class="card-img-top img-fluid">
        <div class="card-body">
            <h4>{{ name }}</h4>
            <div class="poke-type">{{ type }}</div>
            <div class="poke-number">{{ number }}</div>
        </div>
    </div>
</template>

<style></style>