<template>
  <div class="nav-bar">
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'Header',
}
</script>

<style lang="scss" scoped>
.nav-bar {
  background: linear-gradient(-90deg, #84cf6a, #16c0b0);
  height: 60px;
  margin-bottom: 25px;
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.57);
  display: flex;
  align-items: center;
  justify-content: flex-end;
  padding: 1.5rem;
}
</style>
