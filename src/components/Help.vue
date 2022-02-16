<template>
  <div class="help--wrapper">
    <Accordion title="FOIRE AUX QUESTIONS TEDIBER" content='something' />
    <Accordion title="LA GARANTIE TEDIBER" content='something' />
    <Accordion title="REPRISE DE L’ANCIENNE LITERIE" content='something' />
    <Accordion title="COMMENT FAIRE UN RETOUR ?" content='something' />
  </div>
</template>

<script>
  import Accordion from './Accordion.vue'

  export default {
    name: "Help",
    components: {
      Accordion,
    }
  }
</script>

<style lang='scss'>
  @import '../scss/main.scss';

  .help--wrapper {
    width: 90vw;
    margin: 0 auto 2rem auto;
  }

  .help--wrapper:last-child {
    border-bottom: 1px solid $primary-color;
  }
</style>