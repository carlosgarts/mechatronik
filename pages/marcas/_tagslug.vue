<template>
  <div class="container">
    <display v-if="tagId != null " :Modo='3' :searcher='tagName' :tagId='tagId' :tagName='tagName' :key='tagId'/>
  </div>
</template>

<script>
import display from '~/layouts/products/searcher.vue'

export default {
  components: {
    display
  },
  data: function() {
    return {
      tagId: 0,
      tagName: ''
    }
  },
  mounted: async function() {
    var consulta = 'https://blog.mechatronik-group.com/wp-json/wc/v3/products/tags?consumer_key=ck_e9c6d9731b8c0175383bd26c83a495508038d9bc&consumer_secret=cs_3e6da47350b9672250c45d708f7eb2ad15ce013f&slug=';
    consulta = consulta.concat(this.$route.params.tagslug);
    var TagsId = await this.$axios.get(consulta);
    this.tagName = TagsId.data[0].name;
    this.tagId = TagsId.data[0].id;
    console.log(this.tagId);
  }
}
</script>

<style lang="scss" scoped>
  .container {
    background-color: white;
  }
</style>
