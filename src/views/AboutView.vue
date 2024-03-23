<template>

  <nav>
    <router-link to="/">Log In</router-link> 
  
  </nav>
  <router-view/>


  <div>
    <h2>Shopping</h2>
    <!-- Shopping related content goes here -->
    <ProductList :products="products" @add-to-cart="addToCart"></ProductList>
    <Cart :cart-items="cartItems" @remove-from-cart="removeFromCart" @update-quantity="updateQuantity"></Cart>
    <h2 id="totalprice">Total Price: ₱{{ totalPrice }}.00</h2>
  </div>


</template>

<script>
import ProductList from '@/components/ProductList.vue';
import Cart from '@/components/ShopCart.vue';

export default {
  name: 'AboutView',
  components: {
    ProductList,
    Cart
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Panda Ballpen', price: 10 },
        { id: 2, name: 'HBW Ballpen', price: 10 },
        { id: 3, name: 'G-Tech Ballpen', price: 70 },
        { id: 4, name: 'Stabilo Highlighter', price: 50 },
        { id: 5, name: 'Apple Pen', price: 99 }
      ],
      cartItems: []
    };
  },
  computed: {
    totalPrice() {
      return this.cartItems.reduce((total, item) => total + (item.product.price * item.quantity), 0);
    }
  },
  methods: {
    addToCart(product) {
      let existingItem = this.cartItems.find(item => item.product.id === product.id);
      if (existingItem) {
        existingItem.quantity++;
      } else {
        this.cartItems.push({ product: product, quantity: 1 });
      }
    },
    removeFromCart(item) {
      this.cartItems = this.cartItems.filter(cartItem => cartItem !== item);
    },
    updateQuantity({ item, action }) {
      if (action === 'increase') {
        item.quantity++;
      } else if (action === 'decrease') {
        if (item.quantity > 1) {
          item.quantity--;
        }
      }
    }
  }
}
</script>

<style>
#totalprice{
  color: red;
}
</style>
