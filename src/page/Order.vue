<template>
  <Separator :title="orderDB.section.tracking" />
  <OrderInfos :dataProduct="dataProduct" :order="orderDB.order" :tracking="orderDB.tracking" />
  <!--  -->
  <Separator :title="orderDB.section.delivery" />
  <Delivery :data="orderDB.delivery" />
  <!--  -->
  <Separator :title="orderDB.section.payment" />
  <Payment :data="orderDB.order" />
  <!--  -->
  <Separator :title="orderDB.section.total" />
  <Total :data="orderDB.order" />
  <!--  -->
  <Separator :title="orderDB.section.help" />
  <Help />
</template>

<script>
// IMPORT
import orderDB from '../orderTesting.json'
import { onMounted, ref } from '@vue/runtime-core'

// COMPONENT
import Separator from '../components/Separator.vue'
import Delivery from '../components/Delivery.vue'
import Payment from '../components/Payment.vue'
import Total from '../components/Total.vue'
import Help from '../components/Help.vue'
import OrderInfos from '../components/OrderInfos.vue'

export default {
  name:"Order",
  components: {
    Separator,
    Delivery,
    Payment,
    Total,
    Help,
    OrderInfos,
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

</style>