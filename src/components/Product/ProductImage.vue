<template>
  <div><img :src="src" :alt="alt" /></div>
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
