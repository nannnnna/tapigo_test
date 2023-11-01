<template>
    <div v-if="post">
      <img :src="post.image" alt="Post image" />
      <h1>{{ post.title }}</h1>
      <p>{{ post.description }}</p>
      <p>{{ post.date }}</p>
      <ReviewForm />
    </div>
  </template>
  
<script>
import ReviewForm from '~/components/ReviewForm.vue'
  export default {
  components: {
    ReviewForm
    },
    asyncData({ params }) {
      // Здесь можно выполнить запрос к API для получения данных поста по ID
      // Вместо этого мы используем тестовые данные
      return {
        post: {
          id: params.id,
          image: 'https://via.placeholder.com/150',
          title: `Post ${params.id}`,
          description: `Description for post ${params.id}`,
          date: '2023-11-01'
        }
      }
    }
  }
  </script>
  