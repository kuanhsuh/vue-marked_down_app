<template>
  <div>
    <div class="row">
      <div class="col">
        <textarea v-model="input"></textarea>
      </div>
      <div class="col algin-left">
        <div v-html="compiledMarkdown"></div>
      </div>
    </div>
  </div>
</template>
<script>
import marked from 'marked'
export default {
  name: 'main',
  data () {
    return {
      input: '# Heading\n\n## Sub-heading\n\n### Another deeper heading\n\nText attributes _italic_, *italic*, __bold__, **bold**, `monospace`.\n\nHorizontal rule:\n\n---\n\nBullet list:\n* apples\n* oranges\n* pears\n\nNumbered list:\n1. apples\n2. oranges\n3. pears\n\nA [link](http://example.com).'
    }
  },
  computed: {
    compiledMarkdown: function () {
      return marked(this.input, { sanitize: true })
    }
  }
}
</script>
<style scoped>

.algin-left {
  text-align: left;
}
textarea {
  height: 70vh;
  width: 100%;
}
</style>

