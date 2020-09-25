<template>
  <button :class="{ ...type, outlined, block }">{{ text }}</button>
</template>

<script>
require('../../styles/button/main.scss');

export default {
  name: 'S-Button',
  props: {
    text: {
      type: String,
      required: false,
    },
    primary: {
      type: Boolean,
      required: false,
    },
    danger: {
      type: Boolean,
      required: false,
    },
    gray: {
      type: Boolean,
      required: false,
      default: true,
    },
    outlined: {
      type: Boolean,
      required: false,
    },
    block: {
      type: Boolean,
      required: false,
    },
  },
  computed: {
    type() {
      const { primary, danger, gray } = this;

      if (primary || danger) {
        return { primary, danger };
      }
      return { gray };
    },
  },
};
</script>
