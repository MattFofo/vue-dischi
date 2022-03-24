<template>
  <div id="app">
    <HeaderDischi />
    <MainDischi />
  </div>
</template>

<script>
import HeaderDischi from './components/HeaderDischi.vue';
import MainDischi from './components/MainDischi.vue';

export default {
  name: 'App',
  components: {
    HeaderDischi,
    MainDischi,
  },
};
</script>

<style lang="scss">
  $primary: rgb(30,45,59);
  $secondary: rgb(46,58,70);
  @import 'bootstrap';
</style>
