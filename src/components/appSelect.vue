<script >
export default {
    data() {
        return {
            selectedOption: ''
        }
    },
    props: {
        options: Array,
        defaultLabel: String
    }
};
</script>

<template>
    <select v-model="selectedOption">
        <option value="">{{ defaultLabel || '---' }}</option>
        <option v-for="option in options" :key="option">{{ option }}</option>
    </select>
</template>

