<template>
  <div>
    <PostList :posts="posts" @selectPost="selectPost" />
    <PostDetail v-if="selectedPost" :post="selectedPost" />
  </div>
</template>

<script>
import PostList from '~/components/PostList.vue'
import PostDetail from '~/components/PostDetail.vue'

export default {
  components: {
    PostList,
    PostDetail
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          image: 'https://via.placeholder.com/150',
          title: 'Post 1',
          description: 'Description for post 1',
          date: '2023-11-01'
        },
        {
          id: 2,
          image: 'https://via.placeholder.com/150',
          title: 'Post 2',
          description: 'Description for post 2',
          date: '2023-11-02'
        },
        {
          id: 3,
          image: 'https://via.placeholder.com/150',
          title: 'Post 3',
          description: 'Description for post 3',
          date: '2023-11-03'
        }
      ],
      selectedPost: null
    }
  },
  methods: {
    selectPost(post) {
      this.selectedPost = post
    }
  }
}
</script>

<style scoped>
/* Вы можете добавить сюда свой CSS-код */
</style>
