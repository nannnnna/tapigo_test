<template>
    <div>
      <form @submit.prevent="addReview">
        <textarea v-model="newReview" placeholder="Leave a review"></textarea>
        <button type="submit">Submit</button>
      </form>
      
      <div v-for="review in reviews" :key="review.id">
        <p>{{ review.text }}</p>
        
        <div v-if="review.replies.length" class="replies">
          <div v-for="reply in review.replies" :key="reply.id">
            <p>{{ reply.text }}</p>
          </div>
        </div>
        
        <button @click="showReplyForm(review.id)">Reply</button>
        <form v-if="replyingTo === review.id" @submit.prevent="addReply(review.id)">
          <textarea v-model="newReply" placeholder="Leave a reply"></textarea>
          <button type="submit">Reply</button>
        </form>
      </div>
    </div>
  </template>
  
<script>
  export default {
    data() {
      return {
        newReview: '',
        newReply: '',
        replyingTo: null,
        reviews: []
      }
    },
    methods: {
      addReview() {
        this.reviews.push({ id: Date.now(), text: this.newReview, replies: [] })
        this.newReview = ''
      },
      addReply(reviewId) {
        const review = this.reviews.find(r => r.id === reviewId)
        review.replies.push({ id: Date.now(), text: this.newReply })
        this.newReply = ''
        this.replyingTo = null
      },
      showReplyForm(reviewId) {
        this.replyingTo = reviewId
      }
    }
  }
  </script>
  
  <style>
  /* Добавьте свои стили здесь */
  </style>
  