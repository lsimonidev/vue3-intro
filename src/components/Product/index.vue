<template>
  <div class="product-wrapper">
    <ProductImage
      :src="product.variants[product.selectedVariant].image"
      :alt="product.variants[product.selectedVariant].color"
    />
    <div class="product-info">
      <ProductTitle :name="product.name" :brand="product.brand" />
      <p>{{ stockStatus }}</p>
      <p>Shipping: {{ premium ? 'Free' : '2,99' }}</p>
      <ProductDetails :details="product.details" />
      <ProductColors
        :variants="product.variants"
        @variant-hover="updateVariant"
      />
      <Button
        text="Add to Cart"
        :isDisabled="!stock"
        @click="addToCart(product.variants[product.selectedVariant].id)"
      />
    </div>
  </div>
</template>

<script>
import ProductTitle from './ProductTitle'
import ProductImage from './ProductImage'
import ProductDetails from './ProductDetails'
import ProductColors from './ProductColors'
import Button from '../Button'

export default {
  name: 'Product',

  components: {
    ProductTitle,
    ProductImage,
    ProductDetails,
    ProductColors,
    Button,
  },

  props: {
    premium: {
      type: Boolean,
      required: true,
      default: false,
    },
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
            stock: 2,
          },
          {
            id: 2235,
            color: 'blue',
            image: require('@/assets/socks_blue.jpg'),
            stock: 0,
          },
        ],
        reviews: [],
      },
    }
  },

  computed: {
    stock() {
      return this.product.variants[this.product.selectedVariant].stock
    },

    stockStatus() {
      if (this.stock >= 10) {
        return 'In Stock'
      } else if (this.stock > 0) {
        return 'Almost Out'
      } else {
        return 'Out of Stock'
      }
    },
  },

  methods: {
    updateVariant(index) {
      this.product.selectedVariant = index
    },
    addToCart(id) {
      this.product.variants[this.product.selectedVariant].stock--
      this.$emit('add-to-cart', id)
    },
  },
}
</script>

<style lang="scss" scoped>
.product-wrapper {
  @media screen and (min-width: 50rem) {
    display: flex;
  }

  p {
    font-size: 22px;
  }
}
</style>
