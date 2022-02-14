<template>
  <p>PAGE ORDER</p>
  <div class="order--product">
    <p class="numOfProduct">ARTICLES({{dataProduct.length}})</p>
    <ProductCard v-for='(data, i) in dataProduct' :key='i' :productData='data' />
  </div>
</template>

<script>
// IMPORT
import orderDB from '../orderTesting.json'
import { onMounted, ref } from '@vue/runtime-core'
// COMPONENT
import ProductCard from '../components/ProductCard.vue'

export default {
  name:"Order",
  components: {
    ProductCard,
  },
  data() {
    return {
      orderInfos: orderDB.order
    }
  },
    setup() {
    const section = orderDB.section
    const orderInfos = orderDB.order
    const trackingInfos = orderDB.tracking
    // const products = orderDB.product
    const deliveryInfos = orderDB.delivery
    console.log('order infos : ',orderInfos)
    console.log('tracking : ',trackingInfos)
    console.log('delivery : ',deliveryInfos)
    console.log('section : ',section)




// GO PRODUCT CARD
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

    const loadProducts = () => {
      for(const product of orderDB.product) {
        const newProduct = new Product(product.name,product.price,product.size,product.quantity,product.img)
        dataProduct.value.push(newProduct)
      }
    }
// PRODUCT CARD FINISH

    onMounted(loadProducts)
    return {
      dataProduct
    }
  }
}
</script>

<style>
.order--product {
  width: 90vw;
  margin: 0 auto;
}
</style>