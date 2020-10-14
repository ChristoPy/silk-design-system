<template>
  <label :class="state">{{ label }}
    <input type="checkbox" :name="name" v-model="checked">
    <span class="status-area"></span>
  </label>
</template>

<script>
require('../../styles/radio/main.scss');

export default {
  name: 'S-Radio',
  props: {
    name: {
      type: String,
      required: true,
    },
    label: {
      type: String,
      required: true,
    },
    disabled: {
      type: Boolean,
      required: false,
      default: false,
    },
    value: {
      type: Boolean,
      required: false,
      default: false,
    },
  },
  data: () => ({
    checked: false,
  }),
  created() {
    this.checked = this.value;
  },
  computed: {
    state() {
      const classes = {
        'radio-area': true,
      };

      if (this.disabled) {
        classes.disabled = true;
      }

      return classes;
    },
  },
  watch: {
    checked(newValue) {
      this.$emit('input', newValue);
    },
    value(newValue) {
      if (newValue !== this.checked) {
        this.checked = newValue;
      }
    },
  },
};
</script>
