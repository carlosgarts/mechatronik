<template>
  <div class="container">
      <BlogReader/>
  </div>
</template>

<script>
import BlogReader from '~/layouts/blog/blog-reader.vue'

export default {
  components: {
    BlogReader
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
