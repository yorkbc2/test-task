<template>
  <div id="app">
    <app-view></app-view>
  </div>
</template>

<script>
import ViewComponent from "./components/ViewComponent.vue"
import Vue from "vue"

Vue.component("app-view", ViewComponent)


export default {
  name: 'app'
}
</script>

<style>
#app {
  font-family: "Oswald", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
