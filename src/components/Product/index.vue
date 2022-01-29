<template>
  <div class="product-wrapper">
    <ProductImage
      :src="product.variants[product.selectedVariant].image"
      :alt="product.variants[product.selectedVariant].color"
    />
    <ProductTitle
      :name="product.name"
      :brand="product.brand"
      @mouseover="print"
    />
  </div>
</template>

<script>
import ProductTitle from './ProductTitle'
import ProductImage from './ProductImage'

export default {
  name: 'Product',

  components: {
    ProductTitle,
    ProductImage,
  },
  data() {
    return {
      product: {
        name: 'Socks',
        brand: 'Vue Mastery',
        selectedVariant: 0,
        details: ['50% cotton', '30% wool', '20% polyester'],
        variants: [
          {
            id: 2234,
            color: 'green',
            image: require('@/assets/socks_green.jpg'),
            quantity: 50,
          },
          {
            id: 2235,
            color: 'blue',
            image: require('@/assets/socks_blue.jpg'),
            quantity: 0,
          },
        ],
        reviews: [],
      },
    }
  },
  methods: {
    print() {
      console.log(this.product.variants[this.product.selectedVariant].image)
    },
  },
}
</script>

<style lang="scss" scoped>
.product-wrapper {
  display: flex;
  & > * {
    width: 50%;
  }
}
</style>
