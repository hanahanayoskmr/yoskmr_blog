<template>
  <section class="slug">
    <h1 class="slug_title">
      {{ article.fields.title }}
    </h1>
    <p class="slug_date">article.sys.postAt</p>
    <div>
      {{article.fields.body.content[0].content[0].value}}
    </div>
  </section>
</template>


<script>
import { createClient } from '~/plugins/contentful.js'

const client = createClient()
export default {
  transition: 'bounce',
  props: {
    id: {
      type: String,
      default: ''
    }
  },
  transition: 'slide-right',
  async asyncData({ env, params }) {
    return await client
      .getEntry(params.sys)
      .then(entrie => {
        return {
          article: entrie
        }
      })
      .catch(console.error)
  }
}
</script>

<style scoped>
.slug {
  max-width: 800px;
  margin: 0 auto;
}
.slug_title {
  font-size: 2.0rem;
  font-weight: bolder;
}
.slug_date {
  font-size: 1.0rem;
  color: rgb(57, 72, 85);
  text-align: right;
}
</style>