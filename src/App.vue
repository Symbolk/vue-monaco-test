<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <MonacoEditorVue></MonacoEditorVue>
    <VueMonaco></VueMonaco>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MonacoEditorVue from './components/MonacoEditorVue.vue'
import VueMonaco from './components/VueMonaco.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    MonacoEditorVue,
    VueMonaco
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
