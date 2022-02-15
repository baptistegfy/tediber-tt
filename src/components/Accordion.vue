<template>
  <div class="accordion">
    <p>{{title}}</p>
    <img src="../assets/chevron-down.svg">
  </div>
</template>

<script>
export default {
  name:"Accordion",
  props: {
    title: String,
  }
}
</script>

<style lang='scss'>
.accordion {
  width: 100%;
  border-top: 1px solid black;
  border-bottom: 1px solid black;
  display: flex;
  justify-content: space-between;
  align-items: center;
  img {
    height: 2rem;
    padding: 0.25rem 0;
  }
}
</style>