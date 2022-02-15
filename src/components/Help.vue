<template>
  <div class="help--wrapper">
    <Accordion title="FOIRE AUX QUESTIONS TEDIBER"/>
    <Accordion title="LA GARANTIE TEDIBER"/>
    <Accordion title="REPRISE DE L’ANCIENNE LITERIE"/>
    <Accordion title="COMMENT FAIRE UN RETOUR ?"/>
  </div>
</template>

<script>
import Accordion from './Accordion.vue'

export default {
  name:"Help",
  components:{
    Accordion,
  }
}
</script>

<style>
  .help--wrapper {
    width: 90vw;
    margin: 0 auto 2rem auto;
  }
</style>