<template>
  <div class="separator">
    <hr>
    <span class="separator--title">
      <h3 class="upper">{{title}}</h3>
      <img src="../assets/UI_zigzag.svg">
    </span>
  </div>
</template>

<script>
  export default {
    name:"Separateur",
    props: {
      title: String,
    }
  }
</script>

<style lang='scss'>
  .separator {
    margin: 1.5rem 0;
    display:flex;
    justify-content: center;
    align-items: center;
    position: relative;
    hr {
      height: 1px;
      color: #000;
      position: absolute;
      top: 50%;
      bottom: 50%;
      left: 0;
      right: 0;
    }
  }

  .separator--title {
    display:flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    background-color: #fff;
    z-index: 1;
    padding: 0 0.5rem;

    h3 {
      margin-bottom: 0.5rem;
    }
  }
</style>