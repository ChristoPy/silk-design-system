<template>
  <li class="list-item">
    <div class="title">{{ name }}</div>
    <div v-if="text" class="text">{{ text }}</div>
  </li>
</template>

<script>
export default {
  name: 'S-ListItem',
  props: {
    name: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: false,
    },
  },
};
</script>
