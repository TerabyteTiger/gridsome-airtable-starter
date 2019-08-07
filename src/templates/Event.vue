<template>
  <Layout>
    <h1>{{$page.event.name}}</h1>
  </Layout>
</template>

<script>
import Layout from '~/layouts/Default.vue'
export default {
  components: {
    Layout
  },
  metaInfo() {
    return {
      title: this.$page.event.name
    }
  }
}
</script>

<page-query>
query Event ($id: String!) {
  event: event(id: $id) {
    id
    name
    path
    startDate
    endDate
  }
}
</page-query>