<template>
  <div id="app">
    <customFormDemo />
  </div>
</template>

<script>
import CustomFormDemo from '@/components/CustomFormDemo'
export default {
  name: 'App',
  components: { CustomFormDemo }
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
