<template>
  <div class='product--card'>
    <div :style="{ 'background-image': 'url(' + require('../assets/' + productData.img) + ')' }" class="product--img" />
    <div class="product--info">
      <h3 class='product--title'>{{productData.name}}</h3>
      <p class="product--price">{{productData.price}}</p>
      <p class="product--size">TAILLE: {{productData.size}}</p>
      <p class="product--quantity">QTÉ: {{productData.quantity}}</p>
    </div>
  </div>
</template>

<script>
// IMPORT 

export default {
  name: 'ProductCard',
  props: {
    productData: Object
  },
}
</script>

<style lang='scss'>
  .product--card {
    display: flex;
    width: 100%;
    margin: 0.75rem auto;
    padding: 0.5rem;
    box-shadow: 0px 2px 9px rgba(0,0,9px,0.3);
  }

  .product--img {
    width: 116px;
    height: 103px;
    margin-right: 1rem;
    background-size: cover;
    background-position: center;
  }

  .product--info {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
</style>