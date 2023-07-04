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
        <img :src="image" :alt="name" class="card-img-top img-fluid shadow">
        <div class="card-body">
            <h4>{{ name }}</h4>
            <div class="poke-type">{{ type }}</div>
            <div class="poke-number">{{ number }}</div>
        </div>
    </div>
</template>

<style scoped lang="scss">
h4 {
    &::after {
        content: '';
        width: 98%;
        height: 1px;
        display: block;
        margin: 1rem auto;
        background-color: rgba(128, 128, 128, 0.5);
    }
}
</style>