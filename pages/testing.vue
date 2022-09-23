<template>
    <div>
        {{exp()}}
    </div>
</template>

<script>
export default {
    layout: "main",
    methods: {
        exp() {
            return 123
        }
    },
    // mounted() {
    //     this.exp()
    // }
}
</script>

<style scoped>
div {
    width: 100%;
    height: calc(100vh - 56px);
    background-color: bisque;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
