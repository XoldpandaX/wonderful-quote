<template>
  <div id="app">
    <quotes-app></quotes-app>
  </div>
</template>

<script>
  import QuotesApp from './components/QuotesApp.vue';

  export default {
    components: {
      QuotesApp
    }
  }
</script>

<style lang="scss">
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    margin: 60px auto;
    max-width: 1120px;
  }

</style>
