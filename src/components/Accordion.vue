<template>
  <div class="accordion">
    <div class="accordion--top" @click="toggleAccordion()">
      <p>{{title}}</p>
      <img src="../assets/chevron-down.svg">
    </div>
    <div class="accordion--content" v-if="isOpen && content === 'tracking'">
      <span>
        <img class="accordion--icon" src="../assets/order_step_1.svg" alt="">
        <img class="accordion--checkbox" :src="require('../assets/checked-checkbox.svg')"
          v-if="tracking.step1 === true" />
        <img class="accordion--checkbox" :src="require('../assets/checkbox.svg')" v-else />
      </span>
      <span>
        <img class="accordion--icon" src="../assets/order_step_2.svg" alt="">
        <img class="accordion--checkbox" :src="require('../assets/checked-checkbox.svg')"
          v-if="tracking.step2 === true" />
        <img class="accordion--checkbox" :src="require('../assets/checkbox.svg')" v-else />
      </span>
      <span>
        <img class="accordion--icon" src="../assets/order_step_3.svg" alt="">
        <img class="accordion--checkbox" :src="require('../assets/checked-checkbox.svg')"
          v-if="tracking.step3 === true" />
        <img class="accordion--checkbox" :src="require('../assets/checkbox.svg')" v-else />
      </span>
      <span>
        <img class="accordion--icon" src="../assets/order_step_4.svg" alt="">
        <img class="accordion--checkbox" :src="require('../assets/checked-checkbox.svg')"
          v-if="tracking.step4 === true" />
        <img class="accordion--checkbox" :src="require('../assets/checkbox.svg')" v-else />
      </span>
    </div>
    <div class="accordion--content" v-if="isOpen && content === 'something'">
      <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nihil vero, praesentium at, voluptatibus libero
        reiciendis id, nulla corrupti sapiente alias voluptas quod? Suscipit impedit atque, at nisi nam rem qui?</p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Accordion",
    props: {
      title: String,
      content: String,
      tracking: Object
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
    border-top: 1px solid $primary-color;
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
      justify-content: space-between;
      margin-top: 1rem;

      p {
        margin-bottom: 1rem;
        line-height: 1.5;
      }

      span {
        margin-bottom: 1.5rem;
        width: 20%;
        height: 8rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;

        .accordion--icon {
          max-width: 100%;
          height: 4rem;
        }

        .accordion-checkbox {
          height: 2rem;
        }
      }
    }
  }
</style>