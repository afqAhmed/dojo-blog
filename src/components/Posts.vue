<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <single-post :post="post"/>
    </div>
  </div>
</template>

<script>
import SinglePost from './SinglePost.vue'

export default {
  name: 'Posts',
  components: { SinglePost },
  props: ['posts'],
  setup(props) {
    console.log(props)
  }

}
</script>