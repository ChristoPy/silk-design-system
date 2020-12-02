<template>
  <div id="app">
    <slot/>
  </div>
</template>

<script>
require('@/styles/reset/main.scss');
require('@/styles/typography/main.scss');

export default {
  name: 'S-App',
};
</script>

<style lang="scss">
#app {
  padding: .5em 1em;
}
</style>
