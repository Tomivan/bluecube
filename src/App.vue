<template>
  <Sidebar />
  <Home />
</template>

<script>
import Home from './components/Home.vue'
import Sidebar from './components/sidebar.vue'

export default {
  name: 'App',
  components: {
    Home,
    Sidebar
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  display: flex;
}
</style>
