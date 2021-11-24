<template>
  <div>
    <h1>Home Page</h1>
    <h2 class="text-blue-500">Refs Example</h2>
    <p>{{ ninjaOne.name }} -- {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne" class="block bg-gray-400 mt-4 p-2 rounded-lg">Click Me</button>
    <h2 class="text-blue-500">Reactive Example</h2>
    <p>{{ninjaTwo.name}} -> {{ninjaTwo.age}}</p>
    <button @click="updateNinjaTwo" class="block bg-gray-400 mt-4 p-2 rounded-lg">Click Me</button>
  </div>
</template>

<script>
import { reactive, ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    const ninjaOne = ref({
      name: 'Ashfaq',
      age: 47,
    })
    const ninjaTwo = reactive({
      name: 'Susan',
      age: 37,
    })
    const updateNinjaOne = () => {
      ninjaOne.value.age = 46
    }
    const updateNinjaTwo = () => {
      ninjaTwo.age = 38
    }

    return { ninjaOne, ninjaTwo, updateNinjaOne, updateNinjaTwo  }
  },
}
</script>
