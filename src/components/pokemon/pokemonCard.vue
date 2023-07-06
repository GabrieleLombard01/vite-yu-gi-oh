<script>
export default {
    props: {
        name: String,
        image: String,
        type: String,
        number: String,
    },
    data() {
        return {
            isActive: false,
        };
    },
    methods: {
        toggleCardStyle() {
            this.isActive = !this.isActive;
        },
    },
};
</script>

<template>
    <div class="card rounded-4 h-100" :class="{ 'card-active': isActive }" @click="toggleCardStyle">
        <img :src="image" :alt="name" class="card-img-top img-fluid shadow rounded-4">
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

.card {
    transition: border-color 0.3s;
    border: none;
}

.card-active {
    border: solid rgb(10, 238, 10) 5px;
    box-shadow: none;
    border-style: outset;
    cursor: pointer;
}

.card img {
    filter: grayscale(50%);
}

.card:hover img {
    filter: grayscale(0);
}

.card:hover {
    border: solid black 1px;
    border-style: outset;
    cursor: pointer;
}

.card-active img {
    filter: grayscale(0%);
}
</style>