<template>
    <div class="date">
        <span class="day-of-the-week">{{ day }}</span>
        <span class="wrapper">
          <span class="day">{{ date }}</span>
          <span class="mounth">{{ month }}</span>
        </span>
    </div>
  </template>
  
<script>
const months = ['jan', 'fév', 'mar', 'avr', 'mai', 'jun', 'jul', 'aoû', 'sep', 'oct', 'nov', 'dec']
const days = ['dim', 'lun', 'mar', 'mer', 'jeu', 'ven', 'sam']

export default {
  props: {
    dateTime: String,
  },
  computed: {
    date() {
      const date = new Date(this.dateTime)
      return date.getDate()
    },
    day() {
      const date = new Date(this.dateTime)
      return days[date.getDay()].toUpperCase()
    },
    month() {
      const date = new Date(this.dateTime)
      return months[date.getMonth()].toUpperCase()
    },
  }
}
</script>

<style>
.date {
  font-family: "Space Mono", monospace;
}

.day-of-the-week {
  display: block;
  writing-mode: tb-rl
}

.wrapper {
  display: block;
}
</style>