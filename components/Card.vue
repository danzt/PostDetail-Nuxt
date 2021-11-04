<template>
  <div class="px-18 my-12">
    <nuxt-link :to="'post/' + id">
      <div class="c-card block shadow-md hover:shadow-xl rounded-lg overflow-hidden transition delay-150 duration-300 ease-in-out purple-200">
        <div class="relative pb-48 overflow-hidden">
          <img src="https://vilmanunez.com/wp-content/uploads/2013/07/como-escribir-el-post-perfecto-para-tu-blog.png"
          alt="image post" class="absolute inset-0 w-full h-full object-cover">
        </div>
        <div class="p-4 divide-y-4 divide-fuchsia-500">
          <h2 class="mb-2 font-bold font-mono text-lg text-blue-800">{{ title }}</h2>
          <div class="mt-3 flex items-center">
            <p class="text-sm font-semibold mt-3"> Ver detalle</p>
          </div>
        </div>
      </div>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'Card',

  props: {
    title: {
      type: String,
      default: 'Posts'
    },
    alt: {
      type: String,
      default: 'posts detail'
    },
    id: {
      required: true
    }
  },
}
</script>
