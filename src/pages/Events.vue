<template>
  <!-- This is the Events list Page-->
  <Layout>
    <div>
      <div v-for="(edge, index) in $page.events.edges" :key="edge.node.id">
        <EventCard
          :event="edge.node"
          :color="hrColors[index % hrColors.length]"
        />
      </div>
    </div>
  </Layout>
</template>

<page-query>
  query Events {
    events: allEvent (sort: { by: "startDate", order: ASC }){
      edges {
        node{
          id
          name
          startDate
          endDate
          excerpt
          headerImage{
            url
          }
        }
      }
    }
  }
</page-query>

<script>
import Layout from "~/layouts/Default.vue";
import EventCard from "~/components/EventCard.vue";
export default {
  components: {
    Layout,
    EventCard,
  },
  data() {
    return {
      hrColors: [
        "#FCB400", // Airtable Yellow
        "#18BFFF", // Airtable Blue
        "#D92654", // Airtable Red
      ],
    };
  },
};
</script>
