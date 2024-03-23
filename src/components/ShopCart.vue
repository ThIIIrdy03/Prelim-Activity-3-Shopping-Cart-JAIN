<template>
    <div>
      <h2>Cart</h2>
      <div v-for="(item, index) in cartItems" :key="index">
        <p> 
        <button @click="removeFromCart(item)" id="remove">Remove</button>   {{ item.product.name }} - ₱{{ item.product.price }}.00 - Quantity: {{ item.quantity }} 
        <button @click="updateQuantity(item, 'decrease')">-</button>
        <button @click="updateQuantity(item, 'increase')">+</button></p>
       
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: ['cartItems'],
    methods: {
      removeFromCart(item) {
        this.$emit('remove-from-cart', item);
      },
      updateQuantity(item, action) {
        this.$emit('update-quantity', { item, action });
      }
    }
  }
  </script>

  <style>
   #remove{
 
  background-color: #f44336; 
  border: none;
  color: white;
  padding: 5px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;

   }
  </style>
  