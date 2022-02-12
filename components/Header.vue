<template>
      <nav class="relative flex flex-wrap items-center justify-between px-2 py-3 bg-gray-900">
        <div class="container px-4 mx-auto flex flex-wrap items-center justify-between">
          <div class="w-full relative flex justify-between lg:w-auto px-4 lg:static lg:block lg:justify-start">
          <h4 class="flex title-font font-medium text-white hover:text-blue-300 items-center mb-4 md:mb-0">
            <span class="sm:text-2xl">Prof. Juan C. Reyes</span>
          </h4>
            <button class="text-3xl text-grye-900 cursor-pointer text-xl leading-none px-3 py-1 border border-solid border-gray-50 rounded bg-white block lg:hidden outline-none focus:outline-none" type="button" v-on:click="toggleNavbar()">
              <p class="fas fa-bars">&equiv;</p>
            </button>
          </div>
          <div v-bind:class="{'hidden': !menuShow, 'flex': menuShow}" class="lg:flex lg:flex-grow items-center grid justify-items-center">
            <ul class="flex flex-col lg:flex-row list-none justify-items-center lg:ml-auto">
              <nuxt-link to="/" class="py-2 px-6 flex text-white hover:text-blue-300 justify-items-center">Inicio</nuxt-link>
              <nuxt-link to="/blog" class="py-2 px-6 flex text-white hover:text-blue-300 justify-items-center" >Blog</nuxt-link>
              <nuxt-link to="/libros" class="py-2 px-6 flex text-white hover:text-blue-300 justify-items-center">Libros</nuxt-link>
              <nuxt-link to="/materiales" class="py-2 px-6 flex text-white hover:text-blue-300 justify-items-center">Materiales</nuxt-link>
              <nuxt-link to="/actividades" class="py-2 px-6 flex text-white hover:text-blue-300 justify-items-center">Actividades</nuxt-link>
            </ul>
          </div>
        </div>
      </nav>
</template>

<script>
export default {
  name: "pink-menu",
  data() {
    return {
      menuShow: false
    }
  },
  methods: {
    toggleNavbar: function(){
      this.menuShow = !this.menuShow;
    }
  }
}
</script>