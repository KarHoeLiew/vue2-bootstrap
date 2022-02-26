<template>
<div id="checkout-template">

<div>
  <b-card no-body class="card">
    <h1>Item Purchase</h1>
    <h3>1x Orange</h3>
    <h3>1x Strawberry</h3>
    <h3>1x Apple</h3>
    <hr>
    <h3>Subtotal</h3>
    <hr>
    <h1>Delivery</h1>
    <h3>Delivery Area</h3>
    <h3>Delivery Fees</h3>
    <hr>
    <h3>Grandtotal</h3>
    <hr>
    <b-button variant="danger">Place Order</b-button>
  </b-card>
</div>






</div>
</template>

<script>
  export default {
    name: "Checkout",
    components: {},
    data() {
        return {
        
        };
    },
    created() {},
    methods: {},  
    computed: {}
  }
</script>

<style>

.card{
    padding: 10px;
}

hr {
   border: 1px; 
   size: 1px;
}
</style>
