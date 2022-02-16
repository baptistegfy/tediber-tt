<template>
  <div class="accordion">
    <div class="accordion--top" @click="toggleAccordion()">
      <p>{{title}}</p>
      <img src="../assets/chevron-down.svg">
    </div>
    <!--  -->
    <div class="accordion--content" v-if="isOpen && content === 'tracking'">
      <span>
        <img src="../assets/order_step_1.svg" alt="">
        <input type="checkbox" name="" id="" checked>
      </span>
      <span>
        <img src="../assets/order_step_2.svg" alt="">
        <input type="checkbox" name="" id="" checked>
      </span>
      <span>
        <img src="../assets/order_step_3.svg" alt="">
        <input type="checkbox" name="" id="">
      </span>
      <span>
        <img src="../assets/order_step_4.svg" alt="">
        <input type="checkbox" name="" id="">
      </span>
    </div>
    <div class="accordion--content" v-if="isOpen && content === 'something'">
      <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nihil vero, praesentium at, voluptatibus libero reiciendis id, nulla corrupti sapiente alias voluptas quod? Suscipit impedit atque, at nisi nam rem qui?</p>
    </div>
  </div>
</template>

<script>
  export default {
    name:"Accordion",
    props: {
      title: String,
      content: String,
    },
    data() {
      return {
        isOpen: false,
      };
    },
    methods: {
      toggleAccordion() {
        this.isOpen = !this.isOpen;
      },
    },
  }
</script>

<style lang='scss'>
  @import '../scss/main.scss';
  

  .accordion {

    width: 100%;
    border-top: 1px solid black;
    // border-bottom: 1px solid black;
    display: flex;
    flex-direction: column;
    &--top {
      cursor: pointer;
      display: flex;
      justify-content: space-between;
      align-items: center;
      img {
        height: 2rem;
        padding: 0.25rem 0;
      }
    }
    &--content {
      display: flex;
      // display: none;
      justify-content: space-between;
      margin-top: 1rem;
      p {
        margin-bottom: 1rem;
        line-height: 1.5;
      }
      span {
        width: 20%;
        height: 8rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        img {
          max-width: 100%;
          height: 4rem;
        }
        input {
          margin-bottom: 1.5rem;
        }
      }
    }
  }
</style>