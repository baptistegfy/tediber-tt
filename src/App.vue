<template>
  <header class="header">
    <img src="./assets/tediber_logo.svg" class="header--logo">
  </header>
  <Order />
</template>

<script>
//component
import Order from './page/Order.vue'

export default {
  name: 'App',
  components: {
    Order,
  }
}
</script>

<style lang='scss'>
  * {
    box-sizing: border-box;
    margin: 0%;
    padding: 0;
  }

  .header {
    width: 100vw;
    height: 10vh;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0px 2px 9px rgba(0, 0, 0, 0.2);
    &--logo {
      height: 75%;
    }
  }

</style>
