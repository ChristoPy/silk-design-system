<template>
  <div id="app">
    <slot/>
  </div>
</template>

<script>
require('@/styles/reset/main.scss');
require('@/styles/typography/main.scss');

export default {
  name: 'App',
};
</script>
