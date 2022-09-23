<template>
  <section>
    <h2 class="main">
      Main page
    </h2>
  </section>
</template>

<script lang="ts">
import anime from 'animejs';
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  layout: "main",
  methods: {
    strAnime() {
      let str: any = document.querySelector('.main');
      str.innerHTML = str.textContent.replace(/\S/g, "<span>$&</span>");
      anime.timeline({
        easing: 'easeOutExpo',
        loop: true,
      })
        .add({
          targets: '.main span',
          translateX: [0, -1200, 1200, 0],
          opacity: [1, 0, 0, 1],
          duration: 1500,
          scale: [1, 0.1, 0.1, 1],
          delay: anime.stagger(200),
        })
        .add({
          targets: '.main span',
          duration: 800,
          scale: [1, 1.3, 1],
          delay: anime.stagger(100),
        })
    }
  },
  mounted() {
    this.strAnime()
  },
})
</script>

<style>
body {
  background-color: #000063;
}

section {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: calc(100vh - 56px);
  overflow: hidden;
}

section .main {
  position: relative;
  color: #7fffd4;
  font-size: 200px;
  font-weight: 900;
}

section .main span {
  position: relative;
  display: inline-block;
}
</style>
