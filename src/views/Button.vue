<template>
    <button @click="onClick()" :style="{ background: background, color: color }" class="btn shadow">{{buttonText}}</button>
</template>

<script>
    export default {
        name: 'Button',
        props: {
            buttonText: String,
            background: String,
            color: String
        },
        methods: {
            onClick() {
                this.$emit('toggle-add-task')
            },
        },
    }
</script>

<style scoped>

</style>