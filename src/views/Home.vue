<template>
  <div class="container grid justify-center">
    <p v-if="error" class="mt-16 bg-red-200 p-2 rounded">{{ error }}</p>
    <Posts v-if="posts.length" :posts="posts" />
    <p v-else class="text-5xl text-gray-400 mt-32">Loading...</p>
  </div>
</template>

<script>
import Posts from '../components/Posts.vue'
import { ref } from 'vue'

export default {
  name: 'Home',
  components: { Posts },

  setup() {
    const posts = ref([])
    const error = ref()

    const load = async () => {
      try {
        let data = await fetch('http://localhost:3000/posts')
        if (!data.ok) {
          throw Error('Oops! No data available')
        }
        posts.value = await data.json()
      } catch (err) {
        error.value = err.message
        //console.log(error.value)
      }
    }
    load()

    return { posts, error, load }
  },
}
</script>
