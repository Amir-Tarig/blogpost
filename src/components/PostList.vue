<template>
  <div class="post-List">
      <div v-for="post in posts" :key="post.id">
         <single-post :post="post"></single-post>
      </div>
  </div>
</template>

<script>
import SinglePost from './SinglePost.vue'
export default {
  components: { SinglePost },
    props: ['posts'],
}
</script>

<style>

</style>