<template>
  <Header />
  <Order />
</template>

<script>
  //component
  import Order from './page/Order.vue'
  import Header from './components/Header.vue'

  export default {
    name: 'App',
    components: {
      Header,
      Order,
    }
  }
</script>

<style lang='scss'>
  @import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;300;400;700&display=swap');
  @import './scss/main.scss';
</style>
