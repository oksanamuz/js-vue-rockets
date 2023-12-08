<template>
  <button
    v-on:click="$emit('btn-click')"
    type="button"
    :class="['btn', 'btn-primary', 'btn-lg', className]"
  >
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "ButtonComponent",
  props: {
    text: {
      type: String,
      default: "",
    },
    className: {
      type: String,
      default: "",
    },
  },
  emits: ["btn-click"],
};
</script>
