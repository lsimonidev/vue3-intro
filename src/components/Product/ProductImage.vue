<template>
  <div class="product-image"><img :src="src" :alt="alt" /></div>
</template>

<script>
export default {
  name: 'ProductImage',
  props: {
    src: {
      type: String,
      mandatory: true,
    },
    alt: {
      type: String,
      mandatory: true,
    },
  },
}
</script>

<style lang="scss" scoped>
.product-image {
  img {
    border: 2px solid #d8d8d8;
    width: 70%;
    margin: 40px;
    padding: 15px;
    -webkit-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    -moz-box-shadow: 0px 2px 15px -12px rgba(0, 0, 0, 0.57);
    box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
  }
  @media screen and (min-width: 50rem) {
    width: 50%;
  }
}
</style>
