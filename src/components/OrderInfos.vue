<template>
  <div class="order--wrapper">
    <div class="order--infos">
      <p>N° de commande : {{orderDB.order.number}}</p>
      <p>Date de commande : {{orderDB.order.date}}</p>
      <br>
      <hr>
      <p>suivi commande</p>
      <hr>
      <p>informations sur les retours</p>
      <hr>
      <br>
    </div>
    <!--  -->
    <div class="order--product">
      <p class="numOfProduct">ARTICLES({{dataProduct.length}})</p>
      <ProductCard v-for='(data, i) in dataProduct' :key='i' :productData='data'/>
    </div>

  </div>
</template>

<script>
export default {
  name:"OrderInfos",
  props: {
    dataProduct: Array,
  }
}
</script>

<style>

</style>