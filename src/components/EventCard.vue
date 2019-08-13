<template>
  <div 
    class="eventCard" 
    :style="{
      border: '3px solid ' + color
    }"
  >
      <h1 class="handwriting eventTitle">{{ event.name }}</h1>
      <p class="eventDates">{{formattedDate}}</p>
      <p>{{ event.notes }}</p>
      <g-link :to="event.path">More details >></g-link>
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
.eventTitle {
  margin: 0;
}  

.eventCard {
  border-radius: 10px;
  padding: 7px;
  margin-bottom: 15px;
}

.eventDates{
  margin: 0;
  color: hsl(0, 0%, 35%)
}
</style>