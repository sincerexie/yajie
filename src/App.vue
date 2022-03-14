<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import Love from './components/Love.vue';
</script>

<template>
  <Love />
</template>

<style>
#app {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
/* Reset */
html {
  box-sizing: border-box;
  -webkit-text-size-adjust: none;
  font-size: calc(100vw / 3.75);
}
*, *:before, *:after {
  box-sizing: inherit;
 
}
body, h1, h2, h3, h4, h5, h6, p, ol, ul {
  margin: 0;
  padding: 0;
  font-weight: normal;
  font-family: 'Abril Fatface', cursive;

}
:root {
/* colors */
 --yellow: #FFCA74;
 --purple: #664390;
 --red: #FA4843;
 
 --cubezier: 6s cubic-bezier(.52,.02,0,1.02) infinite;
}

body {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  min-height: 100vh;
  overflow-x: hidden;
  background-color: var(--yellow);
  animation: bgRed ease-out 6s infinite;
}
</style>
