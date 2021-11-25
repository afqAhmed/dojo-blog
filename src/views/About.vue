<template>
  <div>
    <h1>About Page</h1>
  </div>
  <input v-model="searchBy" class="border mb-8" type="text">
  <p class="mb-8">Search by - {{ searchBy }}</p>
  <div v-for="name in searchedNames" :key="name">{{ name }}</div>
</template>

<script>
import { ref, computed } from 'vue'

export default {
  name: 'About',
  setup() {
    const names = ref(['Ashfaq', 'Susan', 'Tahia', 'Sanaf', 'Afsheen', 'Mostaquim', 'Ehsan', 'Kawsar'])
    const searchBy = ref('')
    const searchedNames = computed(() => {
      return names.value.filter(name => name.includes(searchBy.value))
    })


    return { names, searchBy, searchedNames }
  }

}
</script>