<template>
  <header class="header">
    <button class="header--burger">btn</button>
    <img src="../assets/tediber_logo.svg" alt="tediber">
    <img class="ours" src="../assets/ours.svg" alt="">
    <ul class="left">
      <li>
        <a class="upper" href="#">nos produits</a>
      </li>
      <li>
        <a class="upper" href="#">le concept</a>
      </li>
      <li>
        <a class="upper" href="#">avis</a>
      </li>
    </ul>
    <ul class="right">
      <li>
        <a class="upper" href="#">pub</a>
      </li>
      <li>
        <a class="upper" href="#">mon compte</a>
      </li>
      <li>
        <a class="upper" href="#">mag</a>
      </li>
      <li>
        <a class="upper" href="#">contactez-nous</a>
      </li>
    </ul>
    <img src="../assets/panier.svg" alt="">
  </header>
</template>

<script>
export default {

}
</script>

<style lang='scss'>
  .header {
    position: relative;
    height: 80px;
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0px 2px 9px rgba(0,0,9px,0.3);
    &--burger {
      display: none;
    }
    img {
      max-height: 100%;
    }
    ul {
      display: flex;
      align-items: center;
      list-style: none;
      height: 100%;
      li {
        margin: 0 0.5rem;
        // height: 100%;
        a {
          text-decoration: none;
          color: #000;
        }
      }
    }
  }
  .left {
    position: absolute;
    left: 0;
  }
  .right {
    position: absolute;
    right: 0;
  }
  .ours {
    height: 50%;
    position: absolute;
    left: 50%;
    transform: translate(-50%);
  }
  // DESKTOP
  @media screen and (min-width: 850px){
  .ours {
    display: none;
  }
  ul {
    visibility: hidden;
  }
  .header {
    &--burger {
      display: block;
    }
  }
}
</style>