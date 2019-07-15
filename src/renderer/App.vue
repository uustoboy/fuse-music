<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: 'fuse-music'
  }
</script>

<style lang="scss">
  /* CSS */
  @import "./node_modules/base_mixins/_base_mixins.scss";
  @include min-base();

</style>
