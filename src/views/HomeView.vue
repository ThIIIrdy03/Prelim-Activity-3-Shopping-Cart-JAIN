<template>
  <center>
  <div>
    <h2>Login</h2>
    <p>input anything :D</p>
    <form @submit.prevent="login">
      <label for="username">Username: </label>
      <input type="text" id="username" v-model="username">
      <br>
      <label for="password">Password: </label>
      <input type="password" id="password" v-model="password">
      <br>
      <br>
      <button type="submit" id="login">Login</button>
     
      
    </form>
  </div>

</center>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: ''
    };
  },
  methods: {
    login() {
      // You can implement your login logic here
      // For simplicity, let's just redirect to shopping page if username and password are not empty
      if (this.username && this.password) {
        this.$router.push('/about');
      } else {
        alert('Invalid username or password');
      }
    }
  }
}
</script>

<style>
#login{
  background-color: #04AA6D; /* Green */
  border: none;
  color: white;
  padding: 5px 20px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
</style>