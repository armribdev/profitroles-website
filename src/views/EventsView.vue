<template>
  <div class="events">
    <h1>Vous êtes sur la page des évènements</h1>
    <div class="event-card">
      <img src="@/assets/logo.svg"/>
      <BaseDateLabel dateTime="2022-11-26 14:45:00"/>
    </div>
  </div>
</template>

<script>
import BaseDateLabel from '@/components/widgets/BaseDateLabel.vue'

export default {
  components: {
    BaseDateLabel,
  },
}
</script>

<style>
</style>