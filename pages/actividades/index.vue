<template>
  <div>
    <Header />
      <div class="container mx-auto px-6 flex flex-col justify-between items-center relative py-8">
        <div class="flex flex-col">
            <h1 class="xl:text-6xl font-black text-gray-900 md:text-5xl md:leading-tight md:font-extrabold">
                Actividades
            </h1>
        </div>
      </div>
    <div>
      <div class="bg-slate-200 w-full  px-5 py-4 space-y-5 sm:py-8 md:py-12 sm:space-y-8 md:space-y-16 max-w-7xl" v-for="tarea of tareas" :key="tareas.slug">
        <nuxt-link :to="{ name: 'actividades-slug', params: { slug: tarea.slug } }">
            <div class="bg-slate-200 container py-4 mx-auto border-2 border-slate-200 border-opacity-60 rounded-lg">
              <div class="my-4 divide-y-2 divide-gray-700">
                <div class="py-6 flex flex-wrap md:flex-nowrap place-content-center">
                  <div class="mx-8 md:w-64 md:mb-0 mb-6 flex-shrink-0 flex flex-col justify-center text-right border-2 border-gray-400 border-opacity-60 rounded-lg px-5 md:justify-center m:text-center place-content-center">
                    <span class="font-semibold text-xl text-gray-700">Curso:</span> <p class="font-semibold text-xl text-gray-900">{{tarea.curso}}</p>
                    <span class="font-semibold text-xl text-gray-700">Area:</span> <p class="font-semibold text-xl text-gray-900">{{tarea.area}}</p>
                    <span class="mt-1 text-gray-500 text-sm">12 Jun 2019</span>
                  </div>
                  <div class="mx-8 md:flex-grow">
                    <h2 class="text-4xl font-black leading-none lg:text-5xl xl:text-4xl xl:text-justify md:text-center">
                      {{ tarea.title }}
                    </h2>
                    <p class="pt-2 mt-8 text-sm text-xl text-xl font-medium text-justify">
                      {{ tarea.description }}
                    </p>
                    <a class="text-indigo-700 inline-flex items-center mt-4"
                      >Leer mas
                      <svg
                        class="w-4 h-4 ml-2"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                        stroke-width="2"
                        fill="none"
                        stroke-linecap="round"
                        stroke-linejoin="round"
                      >
                        <path d="M5 12h14"></path>
                        <path d="M12 5l7 7-7 7"></path>
                      </svg>
                    </a>
                  </div>
                </div>
              </div>
            </div>
        </nuxt-link>
      </div>
    </div>


    <Footer />
  </div>
</template>



<script>
import Header from '~/components/Header.vue'
import Banner from '~/components/Banner.vue'
import Footer from '~/components/Footer.vue'

 
export default {
  components: {
    Header,
    Footer
  }
}
</script>

<script>
  export default {
      async asyncData({ $content, params }) {
          const tareas = await $content('tareas', params.slug)
              .only(['title', 'description', 'img', 'slug', 'curso', 'area'])
              .sortBy('createdAt', 'dec')
              .fetch();
  
          return {
              tareas
          }
      }
  }
</script>

