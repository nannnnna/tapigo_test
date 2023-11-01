<template>
    <form @submit.prevent="submitComment">
      <textarea v-model="commentText"></textarea>
      <button type="submit">Submit</button>
    </form>
  </template>
  
  <script>
  export default {
    data() {
      return {
        commentText: ''
      }
    },
    methods: {
      submitComment() {
        this.$emit('submit-comment', this.commentText)
        this.commentText = ''
      }
    }
  }
  </script>
  