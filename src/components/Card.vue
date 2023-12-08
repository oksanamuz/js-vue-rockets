<template>
  <div :class="['card', className]" :style="{ width: `${width}rem` }">
    <div class="card-body">
      <h5 class="card-title">{{ name }}</h5>
      <p class="card-text">
        {{ description }}
      </p>
      <p class="card-text">Weight: {{ mass.kg }} KG</p>
      <Button @btn-click="$emit('schedule-launch')" text="Schedule Launch" />
    </div>
  </div>
</template>

<script>
import Button from "./Button.vue";
export default {
  name: "CardComponent",
  components: {
    Button,
  },
  emits: ["schedule-launch"],
  props: {
    className: String,
    id: {
      type: String,
      default: "",
    },
    width: {
      type: Number,
      default: 18,
    },
    name: {
      type: String,
      value: "",
    },
    description: {
      type: String,
      value: "",
    },
    mass: {
      type: Object,
    },
  },
};
</script>
