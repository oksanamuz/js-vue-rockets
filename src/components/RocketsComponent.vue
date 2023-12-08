<template>
  <div class="rockets-container">
    <h1>Rockets</h1>
    <CustomButtonComponent
      v-show="!rockets.length"
      @btn-click="$emit('fetch-rockets')"
      text="Load Rockets"
    />
    <div>
      <RocketDetailsComponent
        :rockets="rockets"
      />
    </div>
  </div>
</template>

<script>
import RocketDetailsComponent from "./RocketDetailsComponent.vue";
import CustomButtonComponent from "./CustomButton.vue";
export default {
  name: "RocketsComponent",
  props: {
    rockets: Array,
  },
  emits: ["fetch-rockets"],
  components: {
    RocketDetailsComponent,
    CustomButtonComponent,
  },
  created() {
    console.log(this.rockets, "my rockets");
  },
};
</script>

<style scoped>
.rockets-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background-color: #eeeeee;
  padding: 4rem;
}
</style>
