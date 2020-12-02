<template>
  <section :class="['card', classes]">
    <h3 v-if="title" class="title">{{ title }}</h3>
    <p v-if="text" class="content">{{ text }}</p>
  </section>
</template>

<script>
require('../../styles/card/main.scss');

export default {
  name: 'S-Card',
  props: {
    title: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: false,
    },
    outlined: {
      type: Boolean,
      required: false,
    },
  },
  computed: {
    classes() {
      return {
        'no-content': !this.text,
        outlined: this.outlined,
      };
    },
  },
};
</script>
