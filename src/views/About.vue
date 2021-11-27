<template>
  <div>
    <h1>About Page</h1>
  </div>
  <input v-model="searchBy" class="border my-4" type="text">
  <p class="mb-8">Search by - {{ searchBy }}</p>
  <div v-for="name in searchedNames" :key="name">{{ name }}</div>
  <button @click="handleClick" class="bg-gray-400 px-2 py-1 rounded">Stop Watch</button>
</template>

<script>
import { ref, computed, watch, watchEffect } from 'vue'

export default {
  name: 'About',
  setup() {
    const names = ref(['Ashfaq', 'Susan', 'Tahia', 'Sanaf', 'Afsheen', 'Mostaquim', 'Ehsan', 'Kawsar'])
    const searchBy = ref('')
    const searchedNames = computed(() => {
      return names.value.filter(name => name.includes(searchBy.value))
    })

    // watch(searchBy, () => {
    //   console.log('watch function ran')
    // })


    // watchEffect(() => {
      //   console.log('watchEffect function ran')
    // })
    
    // watchEffect(() => {
      //   console.log('watchEffect function ran', searchBy.value)
    // })

    const stopWatch = watch(searchBy, () => {
      console.log('watch function ran')
    })

    const stopWatchEffect = watchEffect(() => {
      console.log('watchEffect function ran', searchBy.value)
    })

    const handleClick = () => {
      stopWatch()
      stopWatchEffect()
    }





    return { names, searchBy, searchedNames, handleClick }
  }

}
</script>