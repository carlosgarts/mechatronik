<template>
  <div class="container">
      <BlogHeader/>
      <Blog/>
      <BlogFooter/>
  </div>
</template>

<script>
import BlogHeader from '~/layouts/blog/blog-header.vue'
import Blog from '~/layouts/blog/blog.vue'
import BlogFooter from '~/layouts/blog/blog-footer.vue'

export default {
  components: {
    BlogHeader,
    Blog,
    BlogFooter
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
