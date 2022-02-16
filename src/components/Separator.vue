<template>
  <div class="separator">
    <div class="separator--title">
      <h3 class="uppercase">{{title}}</h3>
      <img src="../assets/UI_zigzag.svg">
    </div>
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
  }

  .separator--title {
    display:flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    background-color: #fff;
    z-index: 1;
    padding: 0 0.5rem;
    margin: 1.8rem;
    &::after {
      border-bottom: 0.1rem solid #dedcdc;
      content: " ";
      display: block;
      left: 0;
      margin-left: -0.4rem;
      margin-right: -0.4rem;
      position: absolute;
      top: 2.5rem;
      width: calc(100% + 0.8rem);
    }

    h3 {
      font-weight: 400;
      margin-bottom: 0.5rem;
      z-index: 1;
      background: #fff;
      padding: 0 1rem;
    }
  }

  @media screen and (min-width: 750px){
    .separator {
      margin: 1.5rem 5%;
    }
  }
</style>