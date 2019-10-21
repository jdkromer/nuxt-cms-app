<template>
  <div>
    <div v-for="blogPost in blogPosts" v-bind:key="blogPost.id">
      <nuxt-link :to="blogPost.slug">
        <h1>{{ blogPost.title }}</h1>
      </nuxt-link>
      <br />
    </div>
  </div>
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
