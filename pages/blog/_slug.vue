<template>
  <div>
    <Header />      
      <section class="bg-white">
          <div class="w-full px-5 py-6 mx-auto space-y-5 sm:py-8 md:py-12 sm:space-y-8 md:space-y-16 max-w-7xl">
              <div class="flex flex-col items-center sm:px-5 md:flex-row">
                  <div class="flex flex-col items-start justify-center w-full h-full py-6 mb-6 md:mb-0 md:w-2/3">
                      <div class="flex flex-col items-start justify-center h-full space-y-3 transform md:pl-10 lg:pl-16 md:space-y-5">
                          <div class="bg-pink-500 flex items-center pl-2 pr-3 py-1.5 leading-none rounded-full text-xs font-medium uppercase text-white inline-block">
                              <svg class="w-3.5 h-3.5 mr-1" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"></path></svg>
                              <span>Categoria: </span>
                          </div>
                          <h1 class="text-4xl font-bold leading-none lg:text-5xl xl:text-6xl"><a href="#_">{{ article.title }}</a></h1>
                          <h5 class="pt-2 text-sm font-medium">Autor <a href="#_" class="mr-1 underline">John Doe</a></h5>
                      </div>
                  </div>
                  <div class="w-full md:w-1/3">
                      <a href="#_" class="block">
                          <img class="object-cover w-full h-full rounded-lg max-h-64 sm:max-h-96" src="https://images.unsplash.com/photo-1643509264337-73b834eb377b?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80">
                      </a>
                  </div>
              </div>
          </div>
      </section>
      <article>
        <nuxt-content :document="article" />
      </article>
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
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
		const article = await $content('articles', params.slug).fetch()

		return { article }
	}
}
</script>

<style>
article {
  display: block;
  margin: 0 auto;
  padding: 50px 30px;
  max-width: 1000px;
}

h1 {
  font-size: 44px;
  font-weight: 900;
  margin-bottom: 30px;
}

h2 {
  font-size: 38px;
  font-weight: 900;
  margin-bottom: 30px;
}

h3 {
  font-size: 32px;
  font-weight: 900;
  margin-bottom: 30px;
}

h4 {
  font-size: 28px;
  font-weight: 800;
  margin-bottom: 30px;
}

h5 {
  font-size: 24px;
  font-weight: 800;
  margin-bottom: 30px;
}

h6 {
  font-size: 22px;
  font-weight: 800;
  margin-bottom: 30px;
}

p {
  font-size: 16px;
  font-weight: 400;
  margin-bottom: 36px;
  text-align: justify;
}
blockquote {
  background: #f9f9f9;
  border-left: 10px solid #ccc;
  margin: 1.5em 10px;
  padding: 0.5em 10px;
  quotes: "\201C""\201D""\2018""\2019";
}
blockquote:before {
  color: #ccc;
  content: open-quote;
  font-size: 4em;
  line-height: 0.1em;
  margin-right: 0.25em;
  vertical-align: -0.4em;
}
blockquote p {
  display: inline;
}

ol {
  list-style-type: upper;
  list-style-position: side;
  font-size: 16px;
  font-weight: 600;
  margin-bottom: 20px;
  text-align: justify;
  padding-left: 20px
}
</style>
