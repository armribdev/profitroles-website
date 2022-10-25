<template>
    <span class="dateTimeLabel">
      <span class="dateLabel">
        <span class="day">{{ day }}</span>
        <span class="date-right">
          <span class="date">{{ date }}</span>
          <span class="month">{{ month }}</span>
        </span>
      </span>
      <span class="timeLabel">
        <span class="hours">{{ hours }}</span>
        <span class="time-right">
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
  font-family: "Source Code Pro", "Space Mono", monospace;
  display: flex;
  align-items: center;
  line-height: 1em;
}

.day {
  display: block;
  writing-mode: tb-rl;
  font-size: 1.3em;
  color: lightgray;
  font-weight: 600;
}

.month {
  font-size: 1.2em;
  font-weight: 700;
}

.date {
  font-size: 2em;
  font-weight: 700;
}

.date-right {
  display: flex;
  flex-direction: column;
  line-height: 1.4em;
  align-items: center;
}

.timeLabel {
  margin-left: 1em;
  font-weight: 700;
  display: flex;
  flex-direction: row;
  align-items: end;
}

.hours {
  font-size: 2em;
  font-weight: 700;
}

.bottom {
  font-size: 1.2em;
}

.time-right {
  display: flex;
  flex-direction: column;
  line-height: .8em;
  margin-left: .1em;
}

.timeSeparator {
  color: lightgray;
  font-weight: 700;
  font-size: .7em;
}

.minutes {
  font-weight: 700;
  font-size: 1.2em;
}
</style>