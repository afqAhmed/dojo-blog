<template>
  <div class="max-w-2xl" v-for="post in posts" :key="post.id">
    <single-post :post="post" />
  </div>
</template>

<script>
import SinglePost from './SinglePost.vue'

export default {
  name: 'Post',
  components: { SinglePost },
  props: ['posts'],
  
}
</script>

SinglePostSinglePost
