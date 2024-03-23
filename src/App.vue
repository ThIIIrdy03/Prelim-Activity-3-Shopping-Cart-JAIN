
  <template>
  <!-- <div id="app">
    <ProductList :products="products" @add-to-cart="addToCart"></ProductList>
    <Cart :cart-items="cartItems" @remove-from-cart="removeFromCart" @update-quantity="updateQuantity"></Cart>
    <p>Total Price: {{ totalPrice }}</p>
  </div> -->

  <nav>
   
  
  </nav>
  <router-view/>

</template>

<script>
// import ProductList from './components/ProductList.vue';
// import Cart from './components/ShopCart.vue';

// export default {
//   name: 'App',
//   components: {
//     ProductList,
//     Cart
//   },
//   data() {
//     return {
//       products: [
//         { id: 1, name: 'Product 1', price: 10 },
//         { id: 2, name: 'Product 2', price: 20 },
//         { id: 3, name: 'Product 3', price: 30 }
//       ],
//       cartItems: []
//     };
//   },
//   computed: {
//     totalPrice() {
//       return this.cartItems.reduce((total, item) => total + (item.product.price * item.quantity), 0);
//     }
//   },
//   methods: {
//     addToCart(product) {
//       let existingItem = this.cartItems.find(item => item.product.id === product.id);
//       if (existingItem) {
//         existingItem.quantity++;
//       } else {
//         this.cartItems.push({ product: product, quantity: 1 });
//       }
//     },
//     removeFromCart(item) {
//       this.cartItems = this.cartItems.filter(cartItem => cartItem !== item);
//     },
//     updateQuantity({ item, action }) {
//       if (action === 'increase') {
//         item.quantity++;
//       } else if (action === 'decrease') {
//         if (item.quantity > 1) {
//           item.quantity--;
//         }
//       }
//     }
//   }
// }
</script>

<style>
/* Your styles here */
</style>
