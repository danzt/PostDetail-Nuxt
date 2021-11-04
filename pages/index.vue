<template>
  <div>
    <h1 class="md:text-3xl md:mt-12 font-bold
      text-center leading-6 text-lg">
      Selecciona algun post de tu interes!
    </h1>
      <div class="w-full
          min-h-screen p-10 grid
          grid-cols-1 sm:grid-cols-1
          md:grid-cols-3
          lg:grid-cols-3 xl:grid-cols-3 gap-5 ">
        <Card
          v-for="post in posts.slice(0, 9)"
          :key="post.id"
          :title="post.title"
          :id="post.id"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Index',

  components:{
    Card: () => import('../components/Card.vue'),
  },

  data() {
    return {
      posts: [],
    }
  },
  async fetch() {
    const res = await fetch('https://jsonplaceholder.typicode.com/posts')
    this.posts = await res.json();
    console.log(this.posts)
  },



  head() {
    return {
      title: 'Post In Nuxt',
      meta: [
        { charset: 'utf-8' },
        { name: 'viewport', content: 'width=device-width, initial-scale=1' },
        { hid: 'description', name: 'description', content: 'Nuxt.js project' }
      ],
      link: [
        { rel: 'icon', type: 'image/x-icon', href: '/favicon.ico' }
      ]
    }
  },
}
</script>
