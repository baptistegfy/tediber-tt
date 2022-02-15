<template>
  <div class="total--wrapper">
    <div class="total">
      <div class="priceProducts">
        <p>Sous-total</p>
        <p>{{data.priceProduct}}</p>
      </div>
      <div class="priceDelivery">
        <p>Livraison</p>
        <p>{{data.priceDelivery}}</p>
      </div>
      <div class="priceTotal">
        <p>Total</p>
        <p>{{data.price}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:"Total",
  props:{
    data: Object
  }

}
</script>

<style lang='scss'>
.total--wrapper {
  width: 90vw;
  margin: 0 auto;
}
.total {
  width: 100%;
  padding: 1rem 2rem;
  box-shadow: 0 2px 9px rgba(0,0,9px,0.3); 
}
.priceProducts, .priceDelivery, .priceTotal {
  display: flex;
  justify-content: space-between;
  align-items: center;
  line-height: 2rem;
}

// DESKTOP
@media screen and (min-width: 750px){
  .total {
    padding: 1rem 35%
  }
}
</style>
