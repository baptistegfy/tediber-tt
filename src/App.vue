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
* {
  box-sizing: border-box;
  margin: 0%;
  padding: 0;
}

.upper {
  text-transform: uppercase;
}
</style>
