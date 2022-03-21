<template>
  <main class="layout-container">
    <chess/>
  </main>
</template>

<script>
  import Chess from './components/Chess'

  export default {
    name: 'App',

    components: {
      'chess': Chess
    }
  }
</script>

<style lang="scss">
  @import '@/assets/scss/reset.scss';

  main.layout-container {
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: black;
  }
</style>