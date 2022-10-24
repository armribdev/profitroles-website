<template>
  <div class="events">
    <h1>Découvrez nos prochaines représentations</h1>
    <div class="event-list">
      <EventCard name="Profit'Soirée" type="cabaret" :dateTime="new Date('2022-11-26 14:45:00')"/>
    </div>
  </div>
</template>

<script>
import EventCard from '@/components/EventCard.vue'

export default {
  components: {
    EventCard,
  },
}
</script>

<style scoped>
.events {
  margin: auto;
  text-align: center;
}

.event-list {
  text-align: left;
  margin-top: 4em;
}
</style>