<template>
  <article>
    <h2>{{ $moment(blogPost.date).format('LL') }}</h2>
    <h3>{{ blogPost.title }}</h3>
    <div>{{ blogPost.body }}</div>
  </article>
</template>
<script>
export default {
  async asyncData({ params, payload }) {
    if (payload) return { blogPost: payload }
    else
      return {
        blogPost: await require(`~/assets/content/blog/${params.blog}.json`)
      }
  }
}
</script>
