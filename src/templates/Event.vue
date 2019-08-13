<template>
<!-- This is the Event Details View Page-->
  <Layout>
    <h1 class="handwriting">
      <span class="title--">
        {{$page.event.name}}
      </span>
    </h1>
    
    <span class="date">{{formattedDate}}</span>

    <h2>Details:</h2>
    {{$page.event.notes}}
  </Layout>
</template>

<script>
import moment from 'moment'
import Layout from '~/layouts/Default.vue'

export default {
  components: {
    Layout
  },
  metaInfo() {
    return {
      title: this.$page.event.name
    }
  },
  computed: {
    // The variety of dates is intended as an example of ways to use Moment to get different date formats. 
    // Unused computed values should be removed. 
    formattedStart: function(){
      return moment(this.$page.event.startDate).format("MM/DD/YYYY h:mm A")
    },
    formattedEnd: function(){
      return moment(this.$page.event.endDate).format("MM/DD/YYYY h:mm A")
    },
    formattedDate: function(){
      const start = moment(this.$page.event.startDate).format("MM/DD/YYYY")
      const end = moment(this.$page.event.endDate).format("MM/DD/YYYY")
      if ( start == end ) {
        return moment(this.$page.event.startDate).format("MM/DD/YYYY h:mm A") + " - " + moment(this.$page.event.endDate).format("h:mm A")
      } else {
        return moment(this.$page.event.startDate).format("MM/DD/YYYY h:mm A") + " - " + moment(this.$page.event.endDate).format("MM/DD/YYYY h:mm A")
      }
    }
  },
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
    notes
  }
}
</page-query>

<style scoped>
/* 
"#FCB400", Airtable Yellow
"#18BFFF", Airtable Blue
"#D92654"  Airtable Red 
*/

h1 > span{
  border-bottom: 4px solid #D92654;
  padding-bottom: 4px;
}

h1 {
  margin-bottom: 4px;
}

.date {
  color: hsl(0, 0%, 35%);
}

</style>