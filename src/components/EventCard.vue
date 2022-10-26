<template>
    <div class="event-card" :class="{ 'disabled': isDisabled }">
        <div class="event-poster-wrapper">
          <img class="event-card-poster" :src="`../posters/${posterFilename}`" @click="showFullsceenPoster"/>
          <div class="event-fullscreen-poster-container" @click="hideFullsceenPoster" v-show="!fullscreenHidden">
            <img class="event-fullscreen-poster" src="`../posters/${posterFilename}`"/>
          </div>
        </div>
        <div class="event-card-content">
          <div class="event-card-header">
            <div class="event-card-name">
              <h2 class="event-card-name">{{ name }}</h2>
              <h3 class="event-card-type">{{ type }}</h3>
            </div>
            <BaseDateLabel :dateTime="dateTime"/>
          </div>
          <div class="event-card-description">
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Fugiat voluptatem cumque inventore accusantium quidem praesentium. Delectus repellendus fugit rem nesciunt, soluta, magnam adipisci fugiat tempore repellat unde nostrum facere voluptate.
          </div>
          <div class="event-card-footer">
            <BaseButton :label="buttonText" @click="goToTicketing" :disabled="isDisabled || !ticketingOpen"/>
          </div>
        </div>
    </div>
</template>

<script>
import BaseButton from '@/components/widgets/BaseButton.vue'
import BaseDateLabel from '@/components/widgets/BaseDateLabel.vue'

export default {
  components: {
    BaseDateLabel,
    BaseButton,
  },
  props: {
    name: String,
    type: String,
    dateTime: {
      type: Date,
      required: true,
    },
    ticketingURL: {
      type: String,
      required: false,
      default: '',
    },
    ticketingOpen: {
      type: Boolean,
      required: false,
      default: false,
    },
    posterFilename: {
      type: String,
      required: false,
      default: "poster.png",
    },
  },
  data: function () {
    return {
      fullscreenHidden: true,
    }
  },
  methods: {
    showFullsceenPoster: function (event) {
      this.fullscreenHidden = false;
    },
    hideFullsceenPoster: function (event) {
      this.fullscreenHidden = true;
    },
    goToTicketing: function (event) {
      window.open(this.ticketingURL, '_blank');
    }
  },
  computed: {
    isDisabled() {
      return new Date() > this.dateTime;
    },
    buttonText() {
      if (this.isDisabled)
        return "Billeterie fermée...";
      
      if (this.ticketingOpen)
        return "Réserver mon billet"
      
      return "Billeterie ouverte prochainement...";
    },
    posterSrc() {
      return `../assets/posters/${this.posterFilename}`;
    },
  }
}
</script>

<style scoped>
.event-card {
  margin: auto;
  display: flex;
  background: white;
  color: var(--profitroles-color);
  border-radius: 1em;
  padding: 1em;
  max-width: 840px;
  margin-bottom: 6em;
}

.event-card-poster {
  max-height: 200px;
  max-width: 200px;
  transform: scale(1.5) rotate(-2deg);
  transition: all .1s;
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}

.event-card-poster:hover {
  transform: scale(1.6) rotate(-5deg);
}

.event-card.disabled .event-card-poster {
  filter: grayscale(70%);
}

.event-card.disabled .event-card-poster:hover {
  filter: grayscale(0%);
}

.event-card-content {
  flex: 1
}

.event-card-header {
  display: flex;
  justify-content: space-between;
}

.event-poster-wrapper {
  min-width: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.event-fullscreen-poster-container {
  background-color: rgba(0, 0, 0, 0.95);
  position: fixed;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
}

.event-fullscreen-poster {
  max-height: 100vh;
  max-width: 100vw;
}

.event-card-content {
  display: flex;
  flex-direction: column;
}

.event-card-name {
  font-size: 1.4em;
  margin-bottom: -0.4em;
  font-weight: 600;
}

.event-card-type {
  text-transform: uppercase;
  font-size: 0.8em;
  letter-spacing: 0.2em;
  font-weight: 600;
  color: lightgray;
}


.event-card-description {
  margin-top: 1em;
  flex-grow: 1;
  color: #444;
}

.event-card-footer {
  margin-top: 1em;
  display: flex;
  justify-content: center;
}

.event-card.disabled {
  color: lightgray;
}

.event-card.disabled .event-card-name {
  color: rgb(192, 113, 113);
}

.event-card.disabled .event-card-description {
  color: lightgray;
}

.event-card.disabled .event-card-poster {
  color: lightgray;
}

@media (min-width: 1024px) {
.event-fullscreen-poster {
  max-height: 90vh;
  max-width: 90vw;
}
}
</style>