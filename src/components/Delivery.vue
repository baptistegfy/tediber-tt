<template>
  <section class="delivery--wrapper">
    <div class="delivery">

      <div class="delivery--address">
        <h3>ADRESSE DE COLLECTE</h3>
        <p class="upper">{{data.type}}</p>
        <p>{{data.address}}</p>
        <p class="upper">{{data.city}}</p>
        <p>{{data.postcode}}</p>
        <p>{{data.country}}</p>
      </div>

      <hr>

      <div class="delivery--contact">
        <h3>VOS COORDONÉES</h3>
        <p>{{data.client}}</p>
        <p>{{data.phone}}</p>
      </div>

      <hr>

      <div class="delivery--estimated">
        <h3>LIVRAISON ESTIMÉE</h3>
        <p>{{data.estimatedDelivery ? data.estimatedDelivery : "Pas d'éstimation pour le momment"}}</p>
      </div>

      <hr>
      
      <div class="delivery--mode">
        <h3>MODE DE LIVRAISON</h3>
        <p>{{data.deliveryMode}}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Deliery",
  props: {
    data: Object,
  },
  setup(props) {
    console.log(props)
  }
}

</script>

<style lang='scss'>
.delivery--wrapper{
  width: 90vw;
  margin: 0 auto;
}

.delivery {
  width: 100%;
  padding: 1rem;
  box-shadow: 0px 2px 9px rgba(0,0,9px,0.3);
  
  h3 {
    margin-bottom: 1rem;
  }

  div {
    min-height: 3rem;

    p {
      margin: 0.25rem 0;
    }
  }

  hr {
    margin: 1rem 0;
  }
}
</style>