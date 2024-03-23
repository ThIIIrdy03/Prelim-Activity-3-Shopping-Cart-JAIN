<template>
    <div>
      <h2>Products</h2>
      <div v-for="product in products" :key="product.id">
        <p> <button @click="addToCart(product)" id="addtocart">Add to Cart</button> {{ product.name }} - ₱{{ product.price }}.00</p>     
       
    
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['products'],
    methods: {
      addToCart(product) {
        this.$emit('add-to-cart', product);
      }
    }
  }
  </script>
  
  <style>
  #addtocart{
    background-color: #04AA6D; /* Green */
  border: none;
  color: white;
  padding: 5px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
 
  }
  </style>