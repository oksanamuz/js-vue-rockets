<template>
  <div>
    <LaunchesComponent :launches="launches" @remove-launch="removeLaunch" />

    <RocketsComponent
      :rockets="rockets"
      @fetch-rockets="getRockets"
      @schedule-launch="scheduleLaunch"
    />
  </div>
</template>

<script>
import LaunchesComponent from "./LaunchesComponent.vue";
import RocketsComponent from "./RocketsComponent.vue";

// The SpaceX API URL for fetching rocket data
const SPACE_API_URL = "https://api.spacexdata.com/v4/rockets";

export default {
  name: "SpaceCenterComponent",
  data() {
    return {
      rockets: [],
      launches: [],
    };
  },

  methods: {
    async fetchRockets() {
      // TODO: Fetch data from SPACE_API_URL
      console.log(SPACE_API_URL);
    },

    async getRockets() {
      this.rockets = [];
    },

    removeLaunch(id) {
      this.launches = this.launches.filter(({ id: currId }) => id !== currId);
    },

    // Schedule a launch if it doesn't already exist in the launches array
    scheduleLaunch(rocket) {
      if (!this.launches.some((launch) => launch.id === rocket.id)) {
        this.launches = [...this.launches, rocket];
      }
    },
  },
  components: {
    LaunchesComponent,
    RocketsComponent,
  },
};
</script>
