<template>

  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <MySlider />
</template>

<script>

import MySlider from './components/MySlider.vue'

export default {
  name: 'App',
  components: {
  
    MySlider

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

  
}
</style>
