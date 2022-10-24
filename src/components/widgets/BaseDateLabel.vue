<template>
    <span class="dateTimeLabel">
      <span class="dateLabel">
        <span class="day">{{ day }}</span>
        <span class="right">
          <span class="date">{{ date }}</span>
          <span class="month">{{ month }}</span>
        </span>
      </span>
      <span class="timeLabel">
        <span class="hours">{{ hours }}</span>
        <span class="bottom">
          <span class="timeSeparator">H</span>
          <span class="minutes">{{  minutes }}</span>
        </span>
      </span>
    </span>

  </template>
  
<script>
const months = ['jan', 'fév', 'mar', 'avr', 'mai', 'jun', 'jul', 'aoû', 'sep', 'oct', 'nov', 'dec']
const days = ['dim', 'lun', 'mar', 'mer', 'jeu', 'ven', 'sam']

export default {
  props: {
    dateTime: {
      type: Date,
      required: true,
    },
  },
  computed: {
    date() {
      return this.dateTime.getDate()
    },
    day() {
      return days[this.dateTime.getDay()].toUpperCase()
    },
    month() {
      return months[this.dateTime.getMonth()].toUpperCase()
    },
    hours() {
      return this.dateTime.getHours()
    },
    minutes() {
      return this.dateTime.getMinutes()
    },
  }
}
</script>

<style>
.dateTimeLabel {
  display: flex;
  align-items: center;
  line-height: 1.4em;
  font-weight: bold;
}

.dateLabel {
  font-family: "Space Mono", monospace;
  display: flex;
  align-items: center;
  line-height: 1em;
}

.day {
  display: block;
  writing-mode: tb-rl;
  font-size: 1.3em;
  color: lightgray;
}

.month {
  font-size: 1.2em;
}

.date {
  font-size: 2em;
}

.right {
  display: flex;
  flex-direction: column;
  line-height: 1.4em;
  align-items: center;
}

.timeLabel {
  margin-left: 1em;
}

.hours {
  font-size: 2em;
}

.bottom {
  font-size: 1.2em;
}

.timeSeparator {
  color: lightgray;
}
</style>