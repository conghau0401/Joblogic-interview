<template>
  <div id="app">
    <Header />
    <div id="main">
      <router-view />
    </div>
  </div>
</template>

<script>
  import Header from "@/components/Header.vue";
  export default {
    components: {
      Header,
    }
  };
</script>

<style lang="scss">
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    background: #2e2e36;
  }
  body {
    color: #333;
    font-size: 14px;
    min-width: 1000px;
    max-width: 100%;
    overflow-x: hidden;
    margin: 0 auto;
  }
  img {
    width: 100%;
    height: auto;
  }
</style>
