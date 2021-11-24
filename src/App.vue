<template>
    <Nav />
  <div class="container">
    <p ref="para">My name is {{ name }} and I'm {{ age }} years old.</p>
    <button class="block" @click="handleClick">Click Me</button>
    <input type="text" v-model="name">
    <button @click="age++">Add 1 to age</button>
    <router-view />
  </div>
</template>

<script>
import Nav from './components/Nav.vue'
import { ref } from 'vue'

export default {
  name: 'App',
  components: { Nav },
  setup() {
    // let name = 'Ashfaq'
    // let age = 47
    const name = ref('Ashfaq')
    const age = ref(47)
    
    const para = ref(null)

    const handleClick = () => {
      // console.log(para) // value: p
      // console.log(para.value) // <p>My name is Ashfaq and I'm 47 years old.<p>
      // para.value.classList.add('active')
      // para.value.textContent = 'Oops! you change the content'
      name.value = 'Ashfaq Ahmed'
      age.value = 46
    }

    return { name, age, para, handleClick }
  },
}
</script>
