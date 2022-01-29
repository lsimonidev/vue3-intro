<template>
  <h1>{{ productTitle }}</h1>
</template>

<script>
export default {
  name: 'ProductTitle',
  props: {
    name: {
      type: String,
      mandatory: true,
    },
    brand: {
      type: String,
      mandatory: false,
    },
  },
  computed: {
    productTitle() {
      return this.name + this.brand
    },
  },
}
</script>

<style lang="scss" scoped>
h1 {
  font-size: 50px;
}
</style>
