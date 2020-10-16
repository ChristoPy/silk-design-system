<template>
  <div class="avatar-area">
    <div :class="['avatar', classes]">
      <div class="text" v-if="name && !image">{{ nameAsInitials }}</div>
      <div class="image" v-else>
        <img :src="image" :alt="description">
      </div>
    </div>
  </div>
</template>

<script>
require('../../styles/avatar/main.scss');

export default {
  name: 'S-Avatar',
  props: {
    name: {
      type: String,
      required: false,
    },
    image: {
      type: String,
      required: false,
    },
    description: {
      type: String,
      required: false,
    },
  },
  computed: {
    classes() {
      return {
        'with-text': this.name,
      };
    },
    nameAsInitials() {
      const splittedName = this.name.split(' ');
      let initials = this.getInitialFromString(splittedName[0]);

      if (splittedName.length > 1) {
        const lastSplitted = splittedName.pop();
        initials += this.getInitialFromString(lastSplitted);
      }

      return initials.toUpperCase();
    },
  },
  methods: {
    getInitialFromString(string) {
      return string.substring(0, 1);
    },
  },
};
</script>
