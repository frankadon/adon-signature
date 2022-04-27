<template>
  <input
    class="form-control"
    :type="inputType"
    :name="inputName"
    :placeholder="inputPlaceholder"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>
<script>
export default {
  name: "InputGroup",
  props: {
    inputType: String,
    inputName: String,
    inputPlaceholder: String,
    modelValue: String,
  },
  emits: ["update:modelValue"],
};
</script>

<style scope>
.user-input {
  width: 100%;
  height: 2rem;
  text-indent: 0.5rem;
  border: none;
  border-bottom: 1px solid var(--dark);
}
</style>
