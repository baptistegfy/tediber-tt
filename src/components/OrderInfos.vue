<template>
  <section class="order--wrapper">
    <div class="order--infos">
      <div class="order--info">
        <p>N° de commande : {{order.number}}</p>
        <p>Date de commande : {{order.date}}</p>
      </div>

      <Accordion title="Suivi commande" content='tracking' :tracking="tracking" />
      <Accordion title="Informations sur les retours" content='something' />
    </div>
    <!--  -->
    <div class="order--product">
      <p class="numOfProduct">ARTICLES ({{dataProduct.length}})</p>
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
    order: Object,
    tracking: Object,

  }
}
</script>

<style lang='scss'>
  @import '../scss/main.scss';
.order--wrapper{
  width: 90%;
  margin: 0 auto;
}
  .order--infos {
    height: fit-content;
    border-bottom: 1px solid black;
  }
.order--product {
  margin-top: 2rem;
}

.order--info {
  margin-bottom: 1rem;
  P {
    margin: 1rem 0;
  }
}



// DESKTOP
@media screen and (min-width: 750px){
  .order--wrapper{
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    .order--infos:last-child {
      border-bottom: 1px solid $primary-color; 
    }
  }
  .order--product {
    margin-top: 0;
  }
}
</style>