<template>
  <Layout>
    <div>
      <ul>
        <li v-for="edge in $page.events.edges" :key="edge.node.id">
          <g-link :to="edge.node.path">{{ edge.node.name }}</g-link>
        </li>
      </ul>
    </div>
  </Layout>
</template>

<page-query>
  query Events {
    events: allEvent{
      edges {
        node{
          id
          path
          name
          startDate
          endDate
          headerImage{
            url
          }
        }
      }
    }
  }
</page-query>

<script>
import Layout from '~/layouts/Default.vue'
export default {
  components: {
    Layout
  }
}
</script>
