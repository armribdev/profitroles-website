<template>
    <div class="event-card">
        <div class="event-poster-wrapper">
          <img class="event-card-poster" src="@/assets/posters/poster.png" @click="showFullsceenPoster"/>
          <div class="event-fullscreen-poster-container" @click="hideFullsceenPoster" v-show="!fullscreenHidden">
            <img class="event-fullscreen-poster" src="@/assets/posters/poster.png"/>
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
            <BaseButton label="Réserver mon billet" @click="goToTicketing" />
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
    'name': String,
    'type': String,
    'dateTime': {
      type: Date,
      required: true,
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
      window.open('https://assos.utc.fr/woolly/ventes/', '_blank')
    }
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
}

.event-card-poster {
  max-height: 200px;
  max-width: 200px;
  transform: scale(1.5) rotate(-2deg);
  transition: transform .1s;
  cursor: pointer;
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
}

.event-card-poster:hover {
  transform: scale(1.6) rotate(-5deg);
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
  text-align: center;
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

@media (min-width: 1024px) {
.event-fullscreen-poster {
  max-height: 90vh;
  max-width: 90vw;
}
}
</style>