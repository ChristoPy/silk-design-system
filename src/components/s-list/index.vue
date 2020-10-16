<template>
  <ul class="list">
    <template v-if="items">
      <SListItem v-for="item in items" :key="item.name" :name="item.name" :text="item.text"/>
    </template>
    <slot v-else/>
  </ul>
</template>

<script>
require('../../styles/list/main.scss');

const SListItem = () => import('@/components/s-list-item/index.vue');

export default {
  name: 'SList',
  components: {
    SListItem,
  },
  props: {
    items: {
      type: Array,
      required: false,
    },
  },
};
</script>
