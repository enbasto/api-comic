<template>
  <div id="app">
    <Comic msg="Consumiendo api"/>
  </div>
</template>

<script>
import Comic from './components/Comic.vue';

export default {
  name: 'App',
  components: {
    Comic,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
