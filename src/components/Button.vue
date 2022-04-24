<template>
        <button class="bg-emerald-50 py-2 px-8 mx-2 hover:bg-white">{{ text }}</button>
</template>

<script>
    export default {
        name: 'Button',
        props: {
            text: String,
        }
    }
</script>

<style scoped>

</style>