<template>
  <div class="event-list">
      <EventCard
        v-for="(event, index) in events"
        :name="event.name"
        :type="event.type"
        :posterFilename="event.posterFilename"
        :dateTime="event.dateTime"
        :ticketingURL="event.ticketingURL"
        :ticketingOpen="event.ticketingOpen"
        :key="index"
       />
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'

export default {
  components: {
    EventCard,
  },
  props: {
    events: {
      type: Array,
      required: false,
      default: () => [],
    }
  },
}
</script>

<style scoped>
.event-list {
  text-align: left;
  margin-top: 4em;
}
</style>