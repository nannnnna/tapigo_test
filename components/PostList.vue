<template>
    <div>
      <div v-for="post in posts" :key="post.id">
        <nuxt-link :to="`/posts/${post.id}`">
          <img :src="post.image" alt="Post image" />
          <h2>{{ post.title }}</h2>
          <p>{{ post.description }}</p>
        </nuxt-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      posts: {
        type: Array,
        required: true
      }
    }
  }
  </script>
  