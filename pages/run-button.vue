<template>
    <div>
        <span v-on:mousemove="click" v-on:click="close">
        </span>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import anime from "animejs";

export default Vue.extend({
    layout: 'main',
    methods: {
        click() {
            anime({
                targets: 'span',
                translateX: function () {
                    return anime.random(-500, 500)
                },

                translateY: function () {
                    return anime.random(-200, 300)
                },
                rotate: function () {
                    return anime.random(0, 360)
                },
                duration: 800,
            })
        },
        close() {
            alert('You caught me! You won\'t get it next time')
        }
    },
})
</script>

<style scoped>
span {
    position: absolute;
    top: 200px;
    left: 50%;
    width: 50px;
    height: 50px;
    background-color: brown;
}

span:hover {
    border-radius: 50%;
}

p {
    cursor: pointer;
}
</style>
