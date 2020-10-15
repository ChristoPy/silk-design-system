<template>
  <div class="avatar-area">
    <div class="avatar">
      <div class="text">{{ nameAsInitials }}</div>
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
      required: true,
    },
  },
  computed: {
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
