<template>
  <div class="wrapper">
    <div
      v-for="(variant, index) in variants"
      :key="variant.id"
      @mouseover="updateVariant(index)"
      :style="{ backgroundColor: variant.color }"
      class="color-circle"
    ></div>
  </div>
</template>
<script>
export default {
  name: 'ProductColors',
  props: {
    variants: {
      type: Array,
      required: true,
    },
  },

  methods: {
    updateVariant(index) {
      this.$emit('variant-hover', index)
    },
  },
}
</script>

<style lang="scss" scoped>
.wrapper {
  display: flex;
}
.color-circle {
  width: 50px;
  height: 50px;
  margin-top: 8px;
  border: 2px solid #d8d8d8;
  border-radius: 50%;
}
</style>
