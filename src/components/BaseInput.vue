<script>
export default {
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: [String, Number],
      default: '',
    },
  },
  name: 'BaseInput',
};
</script>

<template>
  <label>{{ label }}</label>
  <input
    v-bind="$attrs"
    :placeholder="label"
    :value="modelValue"
    class="field"
    @input="$emit('update:modelValue', $event.target.value)"
  />
</template>

<style scoped></style>
