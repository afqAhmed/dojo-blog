<template>
  <div class="border my-8 p-4 bg-green-50 rounded-lg shadow-lg hover:shadow-md">
    <h1 class="mb-6">{{ post.title }}</h1>
    <p>{{ snippet }}</p>
  </div>
</template>

<script>
import { computed } from 'vue'

export default {
  name: 'SinglePost',
  props: ['post'],
  setup(props) {
    const snippet = computed(() => {
      return props.post.body.substring(0, 70) + '....'
    })

    return { snippet }
  },
}
</script>
