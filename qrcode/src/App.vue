<template>
  <div id="app">
    <Hello></Hello>
    <Qrcode></Qrcode>
  </div>
</template>

<script>

import Qrcode from './components/qrcode'
import Hello from './components/hello'
export default {
  name: 'App',
  components: {
    Qrcode,Hello
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
