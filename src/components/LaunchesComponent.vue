<template>
  <div className="launches-container">
    <h1>Launches</h1>
    <p>No launches scheduled yet</p>
    <ol>
      <li :key="launch.id" v-for="launch in launches">
        {{ launch.name }} | Weight: {{ launch.mass.kg }} kg
        <Button
            text="X"
            className="mr-2"
        />
      </li>
    </ol>
  </div>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "LaunchesComponent",
  props: {
    launches: Array,
  },
  components: {
    Button,
  },
  emits: ["remove-launch"],
};
</script>

<style scoped>
.launches-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #282c34;
  color: #61dafb;
  padding: 4rem;
}

.launches-container li {
  text-align: left;
}

</style>
