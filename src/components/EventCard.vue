<template>
<!-- This is the Event Card Preview Component-->
  <div 
    class="event--card" 
    :style="{
      border: '3px solid ' + color
    }"
  >
      <h1 class="handwriting event--title">{{ event.name }}</h1>
      <time class="event--dates">{{formattedDate}}</time>
      <p class="event--excerpt">{{ event.excerpt}}</p>
      <div class="link--moreDetails">
        <g-link 
          :to="event.path" 
        > Full Details >></g-link>
      </div>
  </div> 
</template>

<script>
import moment from "moment"
export default {
  name: "EventCard",
  props: {
    event: Object,
    color: String
  },
  computed: {
    // The variety of dates is intended as an example of ways to use Moment to get different date formats. 
    // Unused computed values should be removed. 
    formattedStart: function(){
      return moment(this.event.startDate).format("MM/DD/YYYY h:mm A")
    },
    formattedEnd: function(){
      return moment(this.event.endDate).format("MM/DD/YYYY h:mm A")
    },
    formattedDate: function(){
      const start = moment(this.event.startDate).format("MM/DD/YYYY")
      const end = moment(this.event.endDate).format("MM/DD/YYYY")
      if ( start == end ) {
        return moment(this.event.startDate).format("MM/DD/YYYY h:mm A") + " - " + moment(this.event.endDate).format("h:mm A")
      } else {
        return moment(this.event.startDate).format("MM/DD/YYYY h:mm A") + " - " + moment(this.event.endDate).format("MM/DD/YYYY h:mm A")
      }
    }
  },
}
</script>

<style scoped>
.event--title {
  margin: 0;
}  

.event--date{
  margin: 0;
  color: hsl(0, 0%, 35%);
}

.link--moreDetails{
  display: block;
  padding-right: 25px;
  text-align: right;
}

.event--excerpt {
  /** This converts the `\n`'s into line breaks when *
  *   pulled from Airtable's Long text fields        */
  white-space: pre-wrap;
}

.event--card {
    border-radius: 10px;
    padding: 7px;
    margin-bottom: 15px;
}

@media only screen and (min-width: 500px) {
  .event--card {
    padding: 12px 24px;
  }
}
</style>