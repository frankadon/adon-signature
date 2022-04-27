<template>
  <button
    class="btn btn-primary"
    :style="{ 'background-color': 'var(--' + bgColor + ')' }"
  >
    {{ Text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: {
    Text: String,
    bgColor: String,
  },
};
</script>

<style scope>
</style>