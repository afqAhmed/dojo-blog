<template>
  <div>
    <h1>Home Page</h1>
    <h2 class="text-blue-500">Refs Example</h2>
    <p>{{ ninjaOne.name }} -- {{ ninjaOne.age }}</p>
    <button @click="updateNinjaOne" class="block bg-gray-400 mt-4 p-2 rounded-lg">Click Me</button>
    <h2 class="text-blue-500">Reactive Example</h2>
    <p>{{ninjaTwo.name}} -> {{ninjaTwo.age}}</p>
    <button @click="updateNinjaTwo" class="block bg-gray-400 mt-4 p-2 rounded-lg">Click Me</button>

    <Posts :posts="posts" />
  </div>
</template>

<script>
import { reactive, ref } from 'vue'
import Posts from '../components/Posts.vue'

export default {
  name: 'Home',
  components: { Posts },
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
    const posts = ref([
      { id: 1, title: 'Welcome to the blog', body: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Neque animi quasi a, velit blanditiis porro fugiat inventore eos pariatur ut sint debitis nostrum non rerum asperiores aspernatur natus quos doloribus nihil maxime accusantium assumenda ipsa ipsam. Facere fuga culpa est cum dolore sit consequuntur delectus nostrum repudiandae! Laudantium, quam. Unde, totam quae quia et fuga odio officia adipisci temporibus tempore facilis placeat quo ipsa aut libero eius nobis qui! In pariatur accusantium odio natus vitae a ratione debitis error adipisci nostrum quisquam aliquid deserunt cum voluptas nobis quibusdam consectetur sed eaque, ea qui dolore nihil deleniti vel magnam? Fugiat ipsam fugit necessitatibus porro unde veritatis libero ex omnis. Minima dolorum magnam, eveniet laboriosam voluptatibus blanditiis itaque repellendus, molestias ab corrupti aperiam impedit soluta, reprehenderit atque. Sit nemo ipsa impedit, modi cum facere sint accusantium accusamus laboriosam dolor vel blanditiis quibusdam reiciendis tempore illo ipsam corporis culpa unde explicabo quaerat aliquid! Ad vitae quidem tempora deleniti veniam necessitatibus soluta iure.'},
      { id: 2, title: 'Top 5 CSS tips', body: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Natus, beatae blanditiis dolorem tempora magnam, ducimus soluta laborum enim, quod vitae explicabo deserunt in aspernatur quidem sapiente repellendus magni vero molestias repellat distinctio at quaerat cum quae corrupti! Ad officiis aperiam numquam, suscipit harum dolorum quos in dolores non blanditiis obcaecati quod officia eos at. Tenetur vitae iure voluptas impedit maxime deleniti nesciunt. Eum vitae laborum cupiditate mollitia veniam fugit voluptates accusamus quidem excepturi a commodi corporis, corrupti tenetur quia! Explicabo, distinctio earum et officiis incidunt amet sequi ab laboriosam, corrupti id libero aliquam ex ratione reiciendis? Eos doloribus voluptatibus optio incidunt consectetur libero? Iure voluptatum nihil pariatur expedita recusandae, aut numquam consequuntur tempore tempora culpa delectus ullam officia labore rem harum iusto! Eos minima, expedita dolorum eligendi itaque quasi autem nemo? Autem dolorem labore, enim ipsum incidunt sed. Quam eveniet numquam voluptatum voluptates quia perspiciatis voluptatibus dolore, hic voluptas esse magnam nesciunt delectus maiores doloremque corrupti ipsam laborum, tempore, consectetur nam nemo placeat? Dolore illum nam ipsa doloremque, assumenda ipsum porro distinctio ullam incidunt error nostrum nisi quod ad repudiandae voluptatem, obcaecati mollitia consectetur eos quae quia? Maiores eius nulla dolor, culpa aliquid quas consectetur dolorem est deserunt, doloribus minima!'}
    ])

    return { ninjaOne, ninjaTwo, updateNinjaOne, updateNinjaTwo, posts  }
  },
}
</script>
