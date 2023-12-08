<template>
  <div :class="['card', className]" :style="{ width: `${width}rem` }">
    <div class="card-body">
      <h5 class="card-title">{{ name }}</h5>
      <p class="card-text">
        {{ description }}
      </p>
      <p class="card-text">Weight: {{ mass.kg }} KG</p>
      <CustomButtonComponent @btn-click="$emit('schedule-launch')" text="Schedule Launch" />
    </div>
  </div>
</template>

<script>
import CustomButtonComponent from "./CustomButton.vue";
export default {
  name: "CardComponent",
  components: {
    CustomButtonComponent,
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
