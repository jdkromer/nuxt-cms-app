<template>
  <div>
    <div v-for="blogPost in blogPosts" :key="blogPost.title">
      <nuxt-link :to="blogPost.slug">
        <ul>
          <li>
            <h2>{{ blogPost.title }}</h2>
          </li>
        </ul>
      </nuxt-link>
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
