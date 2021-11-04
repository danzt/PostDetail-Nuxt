<template>
  <div class="min-h-screen grid place-content-center">
    <h1 class="mb-10 text-3xl font-bold text-center leading-6 text-lg"> Detalles del post.</h1>
    <div class="max-w-md mx-auto bg-white rounded-xl shadow-md overflow-hidden md:max-w-2xl">
      <div class="md:flex">
        <div class="md:flex-shrink-0">
          <img class="h-48 w-full object-cover md:w-48" src="https://vilmanunez.com/wp-content/uploads/2013/07/como-escribir-el-post-perfecto-para-tu-blog.png" alt="Image Detail Post">
        </div>
        <div class="p-8">
          <div class="uppercase tracking-wide text-sm text-black font-bold">{{post.title}}</div>
          <p class="mt-2 text-gray-600 ">{{this.post.body}}</p>
        </div>
      </div>
      <nuxt-link to="/">
        <button class="flex-row-reverse mt-5 mx-8 mb-3 align-left bg-blue-600 hover:bg-blue-400 text-white font-bold py-2 px-4 rounded-full">
          Volver
        </button>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        post: [],
      }
    },

    async fetch (){
      const res = await fetch('https://jsonplaceholder.typicode.com/posts/'+this.$route.params.id)
      this.post = await res.json()
      console.log(this.post.title)
    }
  }
</script>
