<template>
    <div class="list-container">
        <h3>Reviews:</h3>
    <ul>
      <li v-for="(review, index) in reviews" :key="index">
        {{ review.name }} gave this {{ review.rating }} stars
        <br/>
        "{{ review.review }}"
        <br/>
      </li>
    </ul>
    </div>
</template>
<script>
export default {
    name: 'review-list',
    props:{
        reviews:{
            type: Array,
        }
    }
}
</script>

<style lang="scss" scoped>
.list-container {
  width: 425px;
  padding: 20px;
  background-color: white;
  box-shadow: 2px 20px -12px rgba(0, 0, 0, 0.57);
  border: 2px solid #d8d8d8;

  li {
  margin-bottom: 30px;
}
}
</style>