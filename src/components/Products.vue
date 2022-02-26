<template>
<div id="products-template">
  <b-container class="bv-example-row" >
  <b-row >
    <b-col cols="4" v-for="product in products" v-bind:key="product._id">

  <b-card
    :title="product.name"
    img-src="https://picsum.photos/600/300/?image=25"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
 >
 <b-row>
    <b-col>    
     <b-card-text>{{product.price}}</b-card-text>
    </b-col>
   <b-col>
    <b-row>
      <b-button href="#" variant="primary">-</b-button>
      <p>0</p>
      <b-button href="#" variant="primary">+</b-button>
    </b-row>
   </b-col>
 </b-row>



  </b-card>
  </b-col>
  </b-row>
</b-container>

</div>

</template>

<script>
  export default {
    name: "Products",
    components: {},
data() {
    return {
      test: "orange.jpg", 
      name: "",
      mobile: "",
      email: "",
      quantity: 0,
      totalSales: 0,
      discountPct: 0,
      pickupArea: 0,
      areaOptions: [
        { value: "0", text: "Mont Kiara" },
        { value: "1", text: "Cheras" },
        { value: "2", text: "Puchong" },
        { value: "3", text: "Kepong" },
        { value: "4", text: "Others" },
      ],
      products: [
        {
          name: "Apple",
          quantity: 0,
          price: 10,
          stock: 0,
          image: "apple.jpg",
        },
        {
          name: "Orange",
          quantity: 0,
          price: 12,
          stock: 0,
          image: "orange.jpg",
        },
        {
          name: "Strawberry",
          quantity: 0,
          price: 9,
          stock: 0,
          image: "strawberry.jpg",
        },
        {
          name: "Strawberry 2",
          quantity: 0,
          price: 7,
          stock: 0,
          image: "strawberry.jpg",
        },
        {
          name: "Orange 2",
          quantity: 0,
          price: 13,
          stock: 0,
          image: "orange.jpg",
        },
        {
          name: "Apple 2",
          quantity: 0,
          price: 11,
          stock: 0,
          image: "apple.jpg",
        },
      ],
    };
  },
    created() {},
    methods: {},  
    computed: {


    }
  }
</script>

<style>
</style>
