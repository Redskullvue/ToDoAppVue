<template>
<div>
  <main-container/>
</div>
</template>

<script>
import MainContainer from './components/main-container.vue'
import "./assets/tailwind.css";
import"./assets/main.css";
import "./assets/sidebar.css"
import "./assets/input.css"
import "./assets/taskbox.css"
export default {
  name: 'App',
  components: {
    MainContainer
  }
}
</script>

<style>
</style>
