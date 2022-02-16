<template>
  <header class="header">
    <div class="header--top">
      <button class="herder--burger" @click="toggleNav()">
        <span></span>
        <span></span>
        <span></span>
      </button>
      <img class="header--tediber" src="../assets/tediber_logo.svg" alt="tediber">
      <img class="header--basket" src="../assets/panier.svg" alt="">
    </div>
    <!--  -->
    <div class="header--responsive" v-if="isOpen"> 
      <ul>
        <li>
          <a href="#">NOS PRODUITS</a>
        </li>
        <li>
          <a href="#">LE CONCEPT</a>
        </li>
        <li>
          <a href="#">AVIS</a>
        </li>
      </ul>
      <img class="header--ours" src="../assets/ours.svg" alt="">
      <ul>
        <li>
          <a href="#">PUB</a>
        </li>
        <li>
          <a href="#">MON COMPTE</a>
        </li>
        <li>
          <a href="#">MAG</a>
        </li>
        <li>
          <a href="#">CONTACTEZ-NOUS</a>
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
  &--top {
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    .herder--burger {
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
    background: #FFF;
    padding: 1rem;
    display: flex;
    align-items: center;
    justify-content: space-between;
    ul {
      list-style: none;
      height: 3rem;
      width: 45%;
      display: flex;
      justify-content: space-around;
      align-items: center;
      li {
        height: 100%;
        display: flex;
        align-items: center;
        a {
          text-decoration: none;
          color: #000;
        }
      }
      li:hover {
        transform: translateY(50px);
      }
    }
    .header--ours {
      height: 3rem;
    }
  }
}

//   .header {
//     position: relative;
//     height: 80px;
//     padding: 1rem;
//     display: flex;
//     justify-content: space-between;
//     align-items: center;
//     box-shadow: 0px 2px 9px rgba(0,0,9px,0.3);
//     &--burger {
//       display: none;
//     }
//     img {
//       max-height: 100%;
//     }
//     ul {
//       display: flex;
//       align-items: center;
//       list-style: none;
//       height: 100%;
//       li {
//         margin: 0 0.5rem;
//         // height: 100%;
//         a {
//           text-decoration: none;
//           color: #000;
//         }
//       }
//     }
//   }
//   .left {
//     position: absolute;
//     left: 0;
//   }
//   .right {
//     position: absolute;
//     right: 0;
//   }
//   .ours {
//     height: 50%;
//     position: absolute;
//     left: 50%;
//     transform: translate(-50%);
//   }
//   // DESKTOP
//   @media screen and (min-width: 850px){
//   .ours {
//     display: none;
//   }
//   ul {
//     visibility: hidden;
//   }
//   .header {
//     &--burger {
//       display: block;
//     }
//   }
// }
</style>