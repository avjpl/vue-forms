<script>
import BaseRadio from '@/components/BaseRadio.vue';

export default {
  name: 'BaseRadioGroup',
  components: { BaseRadio },
  props: {
    options: {
      type: Array,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    modelValue: {
      type: [String, Number],
      required: true,
    },
    vertical: {
      type: Boolean,
      defaultValue: false,
    },
  },
};
</script>

<template>
  <component
    v-for="option in options"
    :key="option.value"
    :is="vertical ? 'div' : 'span'"
    :class="{ horizontal: !vertical }"
  >
    <BaseRadio
      :label="option.label"
      :value="option.value"
      :name="name"
      :modelValue="modelValue"
      @update:modelValue="$emit('update:modelValue', $event)"
    />
  </component>
</template>

<style scoped>
.horizontal {
  margin-right: 20px;
}
</style>
