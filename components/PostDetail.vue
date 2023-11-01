<template>
    <div>
      <img :src="post.image" alt="Post image" />
      <h2>{{ post.title }}</h2>
      <p>{{ post.description }}</p>
      <p>{{ post.date }}</p>
    </div>
  </template>
  
<script>
  export default {
    props: {
      post: Object
    }
  }
</script>
  