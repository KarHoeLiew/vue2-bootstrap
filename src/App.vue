<template>
  <div id="app">
<b-container>
<div>
  <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#"></b-navbar-brand>
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#">Home</b-nav-item>
        <b-nav-item href="#" disabled>Products</b-nav-item>
        <b-nav-item href="#" disabled>MyOrders</b-nav-item>
      </b-navbar-nav>

    </b-collapse>
  </b-navbar>
</div>
  <div class="section">
<b-row>

    <b-col xl="8"><products></products></b-col>
    <b-col xl="4" id="checkout-template"><checkout></checkout></b-col>

</b-row>
  </div>

</b-container>


</div>
</template>

<script>
import Products from './components/Products.vue';
import Checkout from './components/Checkout.vue';
  export default {
    name: "App",
    components: { Products, Checkout},
    data() {
      return {
        user: null
      }
    },
    created() {},
    methods: {},  
    computed: {}
  }
</script>

<style>
#checkout-template{
  padding-left: 0px;
}

.section{
  margin-top: 10px;
}
</style>
