<template>
  <div class="home">
    <h1>Home</h1>
    <div v-if="error"> {{ error }}</div>

    <div v-if="posts.length">
      <post-list :posts="posts"></post-list>
    </div>

    <div v-else>Loading...</div>
  </div>
</template>

<script>
import { computed, ref } from 'vue'
import PostList from '../components/PostList.vue'
import getPosts from '../composables/getPosts'

export default {
  name: 'Home',
  components: {PostList},
  setup() {
    const {posts, error, load } = getPosts()
    load()
    return { posts, error }
  }
 
}
</script>
