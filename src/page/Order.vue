<template>

  <Separator :title="orderDB.section.tracking" />
  <!--  -->
  <!-- <Order /> -->
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


  <Separator :title="orderDB.section.delivery" />
  <Delivery :data="orderDB.delivery" />
  <Separator :title="orderDB.section.payment" />
  <Payment :data="orderDB.order" />
  <Separator :title="orderDB.section.total" />
  <Total :data="orderDB.order" />
  <Separator :title="orderDB.section.help" />
  <Help />



</template>

<script>
// IMPORT
import orderDB from '../orderTesting.json'
import { onMounted, ref } from '@vue/runtime-core'

// COMPONENT
import Separator from '../components/Separator.vue'
import ProductCard from '../components/ProductCard.vue'
import Delivery from '../components/Delivery.vue'
import Payment from '../components/Payment.vue'
import Total from '../components/Total.vue'
import Help from '../components/Help.vue'


export default {
  name:"Order",
  components: {
    ProductCard,
    Separator,
    Delivery,
    Payment,
    Total,
    Help,
  },
  setup() {
    // PRODUCT
    class Product {
      constructor(name,price,size,quantity,img){
        this.name = name
        this.price = price
        this.size = size
        this.quantity = quantity
        this.img = img
      }
    }

    let dataProduct = ref([])

    const loadProductsData = () => {
      for(const product of orderDB.product) {
        const newProduct = new Product(product.name,product.price,product.size,product.quantity,product.img)
        dataProduct.value.push(newProduct)
      }
    }

    // LIFECYCLE
    onMounted(loadProductsData,)

    // RETURN
    return {
      orderDB,
      dataProduct,
    }
  }
}
</script>

<style>
.order--infos, .order--product {
  width: 90vw;
  margin: 0 auto;
}

/* @media screen and (min-width: 1000px){} */
</style>