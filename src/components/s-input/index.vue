<template>
  <div :class="state">
    <label :for="name">{{ label }}</label>
    <input type="text" :name="name" :disabled="!!disabled" v-model="text">
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
    error: {
      type: Boolean,
      required: false,
      default: false,
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
        error: this.error,
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
