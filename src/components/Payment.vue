<template>
  <div class="payment--wrapper">
    <div class="payment">
      <img src="../assets/UI_CB_visa.jpg">
      <p class="upper">{{data.payment}}</p>
    </div>
  </div>
</template>

<script>
  export default {
    name:'Payment',
    props:{
      data: Object,
    }
  }
</script>

<style lang='scss'>
.payment--wrapper {
  width: 90vw;
  margin: 0 auto;
}
.payment {
  width: 100%;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 1rem;
  box-shadow: 0px 2px 9px rgba(0,0,9px,0.3);

  img {
    height: 3rem;
    margin-right: 1rem;
  }
}
</style>