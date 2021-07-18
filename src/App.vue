<template>
<!--  <div id="nav">-->
<!--    <router-link to="/">Home</router-link> |-->
<!--    <router-link to="/about">About</router-link>-->
<!--    <router-link to="/auth"></router-link>-->
<!--  </div>-->
  <router-view/>
</template>

<style>
html, body {
  width: 100%;
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  flex-direction: column;
  position: relative;
  text-align: center;
  min-height: 100%;
  display: flex;
}
</style>
