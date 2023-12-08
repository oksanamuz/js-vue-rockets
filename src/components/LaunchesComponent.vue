<template>
  <div className="launches-container">
    <h1>Launches</h1>
    <p>No launches scheduled yet</p>
    <ol>
      <li :key="launch.id" v-for="launch in launches">
        {{ launch.name }} | Weight: {{ launch.mass.kg }} kg
        <CustomButtonComponent
            text="X"
            className="mr-2"
        />
      </li>
    </ol>
  </div>
</template>

<script>
import CustomButtonComponent from "./CustomButton";
export default {
  name: "LaunchesComponent",
  props: {
    launches: Array,
  },
  components: {
    CustomButtonComponent,
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
