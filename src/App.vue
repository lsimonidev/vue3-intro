<template>
  <div class="app-container">
    <Header>
      <div class="cart">Cart({{ user.cart.length }})</div>
    </Header>

    <Product
      :premium="user.premium"
      :cart="user.cart"
      @add-to-cart="addToCart"
    />
  </div>
</template>

<script>
import Header from './components/Header'
import Product from './components/Product/'

export default {
  name: 'App',
  components: {
    Header,
    Product,
  },

  data() {
    return {
      user: {
        premium: true,
        cart: [],
      },
    }
  },

  methods: {
    addToCart(id) {
      this.user.cart.push(id)
      console.log(this.user.cart)
    },
  },
}
</script>

<style lang="scss">
body {
  background-color: #f2f2f2;
  margin: 0px;
  font-family: tahoma;
  color: #282828;
  .app-container {
    max-width: 64rem;
    margin: auto;
  }
  .cart {
    border: 1px solid #d8d8d8;
    padding: 10px 30px;
    background-color: white;
    box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  }
}
</style>
