<template>
  <li class="list-item">
    <div v-if="avatar" class="left-area">
      <SAvatar :name="avatar.name" :image="avatar.image" :description="avatar.description"/>
    </div>
    <div class="content-area">
      <div class="title">{{ name }}</div>
      <div v-if="text" class="text">{{ text }}</div>
    </div>
  </li>
</template>

<script>
const SAvatar = () => import('@/components/s-avatar/index.vue');

export default {
  name: 'S-ListItem',
  components: {
    SAvatar,
  },
  props: {
    name: {
      type: String,
      required: true,
    },
    text: {
      type: String,
      required: false,
    },
    avatar: {
      type: Object,
      required: false,
    },
  },
};
</script>
