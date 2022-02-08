<template>
  <div>
    <Header />
    <Hero />
    <Body />
    <Footer />
  </div>
</template>
 
<script>
import Header from '~/components/Header.vue'
import Footer from '~/components/Footer.vue'
import Body from '~/components/Body.vue'
import Hero from '~/components/Hero.vue'
 
export default {
  components: {
    Header,
    Footer,
    Hero,
    Body
  }
}
</script>

<script>
  export default {
      async asyncData({ $content, params }) {
          const articles = await $content('articles', params.slug)
              .only(['title', 'description', 'img', 'slug'])
              .sortBy('createdAt', 'asc')
              .fetch();
  
          return {
              articles
          }
      }
  }
</script>

