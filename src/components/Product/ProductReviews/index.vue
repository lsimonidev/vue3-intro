<template>
    <div class="review-container">
        <review-list v-if="reviews.length" :reviews="reviews"/>
        <review-form @review-submitted="addReview"/>
    </div>
</template>
<script>
import ReviewList from './ReviewList.vue'
import ReviewForm from './ReviewForm.vue'

export default {
    name: 'product-reviews',
    components: {
        ReviewList,
        ReviewForm,
    },
    props:{
        reviews:{
            type:Array,
        }
    },
    methods:{
        addReview(productReview){
            this.$emit('review-submitted', productReview)
        }
    }
}
</script>

<style lang="scss" scoped>
.review-container{
    display:flex;
    flex-direction: column;
    gap: 40px;
    margin-left: 40px;
    
    @media screen and (min-width: 50rem) {
        flex-direction: row;
    }
}
</style>