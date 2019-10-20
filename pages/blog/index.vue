<template>
  <article>
    <h1>{{ blogPost.title }}</h1>
    <div>{{ blogPost.body }}</div>
  </article>
</template>
<script>
export default {
  head() {
    return {
      script: [
        { src: 'https://identity.netlify.com/v1/netlify-identity-widget.js' }
      ]
    }
  },
  computed: {
    blogPosts() {
      return this.$store.state.blogPosts
    }
  }
}
</script>
