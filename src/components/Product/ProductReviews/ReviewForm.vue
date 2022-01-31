<template>
    <div class="review-wrapper">
        <form class="review-form" @submit.prevent="onSubmit">
    <h3>Leave a review</h3>
    <label for="name">Name:</label>
    <input id="name" v-model="name">

    <label for="review">Review:</label>      
    <textarea id="review" v-model="review"></textarea>

    <label for="rating">Rating:</label>
    <select id="rating" v-model.number="rating">
      <option>5</option>
      <option>4</option>
      <option>3</option>
      <option>2</option>
      <option>1</option>
    </select>

    <input class="button" type="submit" value="Submit">  

  </form>
    </div>
</template>
<script>
export default {
    name: 'review-form',
    data() {
    return {
      name: '',
      review: '',
      rating: null,
    }
  },
    methods: {
       onSubmit() {
           if (this.name === '' || this.review === '' || this.rating === null) 
           {
                alert('Review is incomplete. Please fill out every field.')
                return
            }

            let productReview = {
                name: this.name,
                review: this.review,
                rating: this.rating,
            }
      
            this.$emit('review-submitted', productReview)

            this.name = ''
            this.review = ''
            this.rating = null
        }
    }
}
</script>

<style lang="scss" scoped>
.review-form {
  display: flex;
  flex-direction: column;
  padding: 20px;
  border: 2px solid #d8d8d8;
  background-color: white;
  box-shadow: 2px 15px -12px rgba(0, 0, 0, 0.57);
}

</style>