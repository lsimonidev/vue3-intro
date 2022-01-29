<template>
  <div class="app-container">
    <Header />
    <Product />
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
}
</script>

<style lang="scss">
body {
  background-color: #f2f2f2;
  margin: 0px;
  font-family: tahoma;
  color: #282828;
}
</style>
