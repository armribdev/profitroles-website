<template>
    <span class="date-time-label">
      <span class="date-label">
        <span class="day">{{ day }}</span>
        <span class="date-right">
          <span class="date">{{ date }}</span>
          <span class="month">{{ month }}</span>
        </span>
      </span>
      <span class="time-label">
        <span class="hours">{{ hours }}</span>
        <span class="time-right">
          <span class="time-separator">H</span>
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
      return this.dateTime.getDate().toString().padStart(2, '0');
    },
    day() {
      return days[this.dateTime.getDay()].toUpperCase();
    },
    month() {
      return months[this.dateTime.getMonth()].toUpperCase();
    },
    hours() {
      return this.dateTime.getHours().toString().padStart(2, '0');
    },
    minutes() {
      return this.dateTime.getMinutes().toString().padStart(2, '0');
    },
  }
}
</script>

<style>
.date-time-label {
  display: flex;
  align-items: center;
  line-height: 1.4em;
  font-weight: bold;
  font-family: "Source Code Pro", "Space Mono", monospace;
}

.date-label {
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

.time-label {
  margin-bottom: 0.4em;
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
}

.time-separator {
  color: lightgray;
  font-weight: 700;
  font-size: .7em;
  margin-left: .1em;
}

.minutes {
  font-weight: 700;
  font-size: 1.2em;
}
</style>