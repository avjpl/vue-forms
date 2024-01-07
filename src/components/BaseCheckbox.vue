<script>
export default {
  name: 'BaseCheckbox',
  props: {
    label: {
      type: String,
      default: '',
    },
    modelValue: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<template>
  <div>
    <input
      type="checkbox"
      :checked="modelValue"
      @change="$emit('update:modelValue', $event.target.checked)"
      class="field"
    />
    <label v-if="label">{{ label }}</label>
  </div>
</template>

<style scoped></style>
