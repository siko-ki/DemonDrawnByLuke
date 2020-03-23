<template>
  <div class="bg">
  <div id="app">
    <div id="menu">
      <div id="brand">
        <router-link to="/home">
          <img src="/images/DEMONDRAWNLOGO.png">
        </router-link>
      </div>
      <router-view id="side">
        <router-link to="/browse">
          <div class="menu-item browse">
            <img src="/images/globe.png">
            <p>Browse</p>
          </div>
        </router-link>
        <router-link to="/cart">
          <div class="menu-item">
            <img src="/images/love.png">
            <p v-if="this.$root.$data.cart && this.$root.$data.cart.length >= 1"> {{ NumberOfItems }} items</p>
            <p v-else> 0 Items </p>
          </div>
        </router-link>
      </router-view>
    </div>
  </div>
  </div>
</template>

<script>
  export default {
    computed: {
      NumberOfItems: function () {
        return this.$root.$data.cart.length;
      }
    },
  }
</script>

<style>
  * {
    box-sizing: border-box;
  }

  body {
    margin: 50px 100px;

  }
  .bg {
    /* The image used */
    background-image: url("/images/Cthulhu HeadShot - Print.png");

    /* Full height */
    height: 100%;

    /* Center and scale the image nicely */
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
  }

  #menu {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-column-gap: 5px;
    grid-template-areas: "none brand side";
    margin-bottom: 50px;
  }

  #menu a {
    color: #B84901;
  }

  #brand {
    grid-area: brand;
    display: flex;
    justify-content: center;
  }

  #brand img {
    height: 200px;
  }

  #side {
    grid-area: side;
    display: flex;
    justify-content: right;
  }

  #side img {
    width: 50px;
  }

  .menu-item {
    display: flex;
    flex-direction: column;
  }

  .menu-item p {
    margin: 0px;
  }

  .browse {
    margin-right: 50px;
  }
</style>
