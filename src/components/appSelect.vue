<script >
export default {
    data() {
        return {
            selectedOption: ''
        }
    },
    props: {
        options: Array,
        defaultLabel: String,
        initialValue: String
    },
    emits: ['option-change'],
    mounted() {
        this.selectedOption = this.initialValue || '';
    }
};
</script>

<template>
    <select v-model="selectedOption" @change="$emit('option-change', selectedOption)">
        <option value="">{{ defaultLabel || '---' }}</option>
        <option v-for="option in options" :key="option">{{ option }}</option>
    </select>
</template>
