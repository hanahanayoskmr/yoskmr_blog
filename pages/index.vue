<template>
  <section class="index">
    <card
      v-for="(post,i ) in posts"
      :key="i"
      :title="post.fields.title"
      :id="post.sys.id"
      :date="post.sys.updatedAt"
    />
  </section>
</template>

<script>
import Card from '~/components/page/card.vue'
import { createClient } from '~/plugins/contentful.js'

const client = createClient()
export default {
  transition: 'bounce',
  components: {
    Card
  },
  asyncData({ env, params }) {
    return client
      .getEntries(env.CTF_BLOG_POST_TYPE_ID)
      .then(entries => {
        return {
          posts: entries.items
        }
      })
      .catch(console.error)
  }
}
</script>

<style scoped>
.index {
  display: flex;
  flex-wrap: wrap;
}
</style>