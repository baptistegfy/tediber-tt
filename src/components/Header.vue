<template>
  <header class="header">
    <div class="header--top">
      <button class="header--burger" @click="toggleNav()">
        <span></span>
        <span></span>
        <span></span>
      </button>

      <img class="header--tediber" src="../assets/tediber_logo.svg" alt="tediber">
      
      <ul class="left-desktop-nav">
        <li>
          <a class="upper" href="#">NOS PRODUITS</a>
        </li>
        <li>
          <a class="upper" href="#">LE CONCEPT</a>
        </li>
        <li>
          <a class="upper" href="#">AVIS</a>
        </li>
      </ul>

      <img class="header--ours" src="../assets/ours.svg" alt="">

      <ul class="right-desktop-nav">
        <li>
          <a class="upper" href="#">PUB</a>
        </li>
        <li>
          <a class="upper" href="#">MON COMPTE</a>
        </li>
        <li>
          <a class="upper" href="#">MAG</a>
        </li>
        <li>
          <a class="upper" href="#">CONTACTEZ-NOUS</a>
        </li>
      </ul>

      <img class="header--basket" src="../assets/panier.svg" alt="">
    </div>
    <!--  -->
    <div class="header--responsive" v-if="isOpen"> 
      <ul>
        <li>
          <a class="upper" href="#">NOS PRODUITS</a>
        </li>
        <li>
          <a class="upper" href="#">LE CONCEPT</a>
        </li>
        <li>
          <a class="upper" href="#">AVIS</a>
        </li>
      </ul>
      <ul>
        <li>
          <a class="upper" href="#">PUB</a>
        </li>
        <li>
          <a class="upper" href="#">MON COMPTE</a>
        </li>
        <li>
          <a class="upper" href="#">MAG</a>
        </li>
        <li>
          <a class="upper" href="#">CONTACTEZ-NOUS</a>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name:'Header',
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    toggleNav() {
      this.isOpen = !this.isOpen
    }
  }
}
</script>

<style lang='scss'>
.header {
  background: #fff;
  z-index: 10;
  position: relative;
  width: 100vw;
  // height: 10vh;
  box-shadow: 0px 2px 9px rgba(0,0,9px,0.3);
  display: flex;
  flex-direction: column;
  .left-desktop-nav,.right-desktop-nav,.header--ours {
    display: none;
  }
  &--top {
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .header--burger {
      height: 100%;
      padding: 1rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      border: none;
      outline: none;
      background: transparent;
      cursor: pointer;
      span {
        width: 2rem;
        height: 2px;
        border: 1px solid black;
        margin: 0.25rem;
      }
    }
    img {
      max-width: 5rem;
      max-height: 100%;
    }
  }
  &--responsive {
    // background: #FFF;
    padding: 1rem;
    ul {
      list-style: none;
      li {  
        a {
          text-decoration: none;
          color: #000;
        }
      }
    }
  }
}

@media screen and (min-width: 1034px){
  .header {
    .header--ours {
      display: block;
    }
    &--responsive {
      display: none;
    }
    .left-desktop-nav,.right-desktop-nav {
      display: flex;
      list-style: none;
      li {
        a {
          text-decoration: none;
          color: #000;
          margin: 0 0.5rem;
        }
      }
    }
  }

  .header--top .header--burger {
    display: none;
  }
  // .header--burger,.header--responsive {
  //   display: none;
  // }


}

</style>