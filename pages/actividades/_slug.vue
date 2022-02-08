<template>
  <div>
    <Header /> 
      <article>
        <nuxt-content :document="tarea" />
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
		const tarea = await $content('tareas', params.slug).fetch()

		return { tarea }
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
  list-style-type: upper-roman;
}
</style>
