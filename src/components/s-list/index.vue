<template>
  <ul class="list">
    <li v-for="item in items" class="list-item" :key="item.name">
      <div class="title">{{ item.name }}</div>
      <div v-if="item.text" class="text">{{ item.text }}</div>
    </li>
  </ul>
</template>

<script>
require('../../styles/list/main.scss');

export default {
  name: 'SList',
  props: {
    items: {
      type: Array,
      required: true,
    },
  },
};
</script>
