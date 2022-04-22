<template>
        <button class="bg-gray-300 py-2 px-8 mx-2 hover:bg-blue-100">{{ text }}</button>
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