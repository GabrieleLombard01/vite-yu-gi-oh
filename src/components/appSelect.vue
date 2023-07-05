<script >
export default {
    props: {
        defaultLabel: String
    }
};
</script>

<template>
    <select>
        <option value="">{{ defaultLabel || '---' }}</option>
        <option>Opzione 1</option>
        <option>Opzione 2</option>
        <option>Opzione 3</option>
    </select>
</template>

<style>
/*CSS reset*/

/*Pseudo-classes*/

/*Generics*/

/*Utilties*/
</style>