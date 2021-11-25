<template>
  <div class="my-4 border rounded p-4">
    <h2 class="my-2">{{ post.title }}</h2>
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
      return props.post.body.substring(0, 70) + '.... '
    })

    return { snippet }
  }
}
</script>
