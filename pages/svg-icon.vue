<template>
    <section>
        <div class="icon">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                <path
                    d="M 4 8 L 10 1 L 13 0 L 12 3 L 5 9 C 6 10 6 11 7 10 C 7 11 8 12 7 12 A 1.42 1.42 0 0 1 6 13 A 5 5 0 0 0 4 10 Q 3.5 9.9 3.5 10.5 T 2 11.8 T 1.2 11 T 2.5 9.5 T 3 9 A 5 5 90 0 0 0 7 A 1.42 1.42 0 0 1 1 6 C 1 5 2 6 3 6 C 2 7 3 7 4 8 M 10 1"
                    stroke="#FF0000" stroke-width="0.1" fill="#ffffff00" />
            </svg>
            <div class="el"></div>
        </div>
    </section>
</template>

<script>
import anime from 'animejs';

export default {
    layout: "main",
    methods: {
        iconAnime() {
            let path = anime.path('.icon svg path');
            // anime({
            //     targets: '.icon .el',
            //     translateX: path('x'),
            //     translateY: path('y'),
            //     rotate: path('angle'),
            //     easing: 'linear',
            //     duration: 5000,
            //     loop: true
            // });
            anime.timeline({
                easing: 'easeInOutSine',
            })
                .add({
                    targets: '.icon svg path',
                    strokeDashoffset: [anime.setDashoffset, 0],
                    delay: function (el, i) { return i * 250 },
                    direction: 'alternate',
                    duration: 30000,
                    delay: anime.stagger(500),
                    // loop: true
                });
        }
    },
    mounted() {
        this.iconAnime()
    },
}
</script>

<style scoped>
.icon {
    position: relative;
    width: 40%;
    height: 500px;
    margin: auto;
}

svg {
    position: absolute;
    top: -138px;
    left: 9px;
    margin-top: 150px;
    width: 100%;
}

.el {
    position: absolute;
    top: 6px;
    left: 3px;
    display: inline-block;
    border-radius: 10% 80% 80% 10%;
    width: 20px;
    height: 8px;
    background-color: burlywood;
}
</style>
