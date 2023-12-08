<template>
  <div>
    <div :key="rocket.id" v-for="rocket in rockets" class="rocketdetails">
      <Card
          width="46"
          className="mt-4"
          :name="rockets[0].name"
          :description="rockets[0].description"
          :mass="rockets[0].mass"
          @schedule-launch="$emit('schedule-launch', rockets[0])"
      />
    </div>
  </div>
</template>

<script>
import Card from './Card.vue';

export default {
  name: 'RocketDetailsComponent',
  props: {
    rockets: Array
  },
  emits: [ 'schedule-launch' ],
  components: { Card }
};
</script>


<style scoped>
  .rocketdetails {
    transform: rotate(-180deg);
  }
</style>
