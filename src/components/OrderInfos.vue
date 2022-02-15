<template>
  <section class="order--wrapper">
    <div class="order--infos">
      <div class="order--info">
        <p>N° de commande : {{order.number}}</p>
        <p>Date de commande : {{order.date}}</p>
      </div>

      <Accordion title="Suivi commande"/>
      <Accordion title="Informations sur les retours"/>
    </div>
    <!--  -->
    <div class="order--product">
      <p class="numOfProduct">ARTICLES({{dataProduct.length}})</p>
      <ProductCard v-for='(data, i) in dataProduct' :key='i' :productData='data'/>
    </div>
    
  </section>
</template>

<script>
import Accordion from './Accordion.vue'
import ProductCard from './ProductCard.vue'
export default {
  name:"OrderInfos",
  components: {
    Accordion,
    ProductCard,
  },
  props: {
    dataProduct: Array,
    order: Object
  }
}
</script>

<style lang='scss'>
.order--wrapper{
  width: 90%;
  margin: 0 auto;
}
.order--product {
  margin-top: 2rem;
}

.order--info {
  margin-bottom: 1rem;
}

// DESKTOP
@media screen and (min-width: 750px){
  .order--wrapper{
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
  }
  .order--product {
    margin-top: 0;
  }
}
</style>