<template>
  <header class="shadow-sm">
    <nav class="relative flex flex-wrap items-center justify-between px-2 py-3">
      <div class="container px-4 mx-auto flex flex-wrap items-center justify-between">
        <div class="w-full relative flex justify-between lg:w-auto px-4 lg:static lg:block lg:justify-start">
        <h4 class="flex title-font font-medium hover:text-blue-300 items-center mb-4 md:mb-0">
          <span class="sm:text-2xl">Prof. Juan C. Reyes</span>
        </h4>
          <div class="lg:hidden">
          <button class="p-2 text-gray-600 bg-gray-100 rounded-lg"  v-on:click="toggleNavbar()" type="button">
            <span class="sr-only">Menu</span>
            <svg
              aria-hidden="true"
              class="w-5 h-5"
              fill="none"
              stroke="currentColor"
              viewbox="0 0 24 24"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path d="M4 6h16M4 12h16M4 18h16" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" />
            </svg>
          </button>
          
        </div>
        </div>
        <div v-bind:class="{'hidden': !menuShow, 'flex': menuShow}" class="lg:flex lg:flex-grow items-center">
          <ul class="flex flex-col lg:flex-row list-none justify-items-center text-center lg:ml-auto">
              <nuxt-link to="/" class="py-2 px-6 flex hover:text-blue-700">Inicio</nuxt-link>
              <nuxt-link to="/blog" class="py-2 px-6 flex hover:text-blue-700">Blog</nuxt-link>
              <nuxt-link to="/libros" class="py-2 px-6 flex hover:text-blue-700">Libros</nuxt-link>
              <nuxt-link to="/materiales" class="py-2 px-6 flex hover:text-blue-700">Materiales</nuxt-link>
              <nuxt-link to="/actividades" class="py-2 px-6 flex hover:text-blue-700">Actividades</nuxt-link>
          </ul>
        </div>
      </div>
    </nav>
  </header>
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