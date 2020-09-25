<template>
  <div :class="state">
    <label :for="name">{{ label }}</label>
    <input type="text" :disabled="!!disabled" v-model="text">
    <small v-show="hint">{{ hint }}</small>
  </div>
</template>

<script>
require('../../styles/input/main.scss');

export default {
  name: 'S-Input',
  props: {
    name: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    hint: {
      type: String,
      required: false,
    },
    disabled: {
      type: Boolean,
      required: false,
      default: false,
    },
    value: {
      type: String,
      required: false,
      default: '',
    },
  },
  data: () => ({
    text: '',
  }),
  created() {
    this.text = this.value;
  },
  computed: {
    state() {
      const classes = {
        'input-area': true,
      };

      if (this.disabled) {
        classes.disabled = true;
      }

      return classes;
    },
  },
  watch: {
    text(newValue) {
      this.$emit('input', newValue);
    },
    value(newValue) {
      if (newValue !== this.text) {
        this.text = newValue;
      }
    },
  },
};
</script>
