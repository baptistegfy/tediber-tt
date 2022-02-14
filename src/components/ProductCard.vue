<template>
  <div class='product--card'>
    <div :style="changeBg" class="product--img"></div>
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
import { computed } from 'vue'

export default {
  name: 'ProductCard',
  props: {
    productData: Object
  },
  setup(props) {
    // console.log(props.productData.img)
    const changeBg = computed(() => {
      return {
        backgroundImage: `url(${props.productData.img}`
      }
    })
    return {
    changeBg
    }
  }
}
</script>

<style lang='scss'>
  .product--card {
    display: flex;
    width: 100%;
    margin: 0.75rem auto;
    padding: 0.5rem;
    box-shadow: 0px 0px 9px rgba(0,0,9px,0.2)
  }

  .product--img {
    width: 116px;
    height: 103px;
    margin-right: 1rem;
    background-size: cover;
    background-position: center;
    background-image: url('../assets/Tediber-mattress.jpg');
    background-color: #C4C4C4;
  }
</style>