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
  @include min-base();

  @font-face {font-family: "element-icons";
    src: url('./assets/css/iconfont/iconfont.eot?t=1563342089617'); /* IE9 */
    src: url('./assets/css/iconfont/iconfont.eot?t=1563342089617#iefix') format('embedded-opentype'), /* IE6-IE8 */
    url('data:application/x-font-woff2;charset=utf-8;base64,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') format('woff2'),
    url('./assets/css/iconfont/iconfont.woff?t=1563342089617') format('woff'),
    url('./assets/css/iconfont/iconfont.ttf?t=1563342089617') format('truetype'), /* chrome, firefox, opera, Safari, Android, iOS 4.2+ */
    url('./assets/css/iconfont/iconfont.svg?t=1563342089617#element-icons') format('svg'); /* iOS 4.1- */
  }

  .element-icons {
    font-family: "element-icons" !important;
    font-size: 16px;
    font-style: normal;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #fff;
  }

  .el-icon-zanting:before {
    content: "\e638";
  }

  .el-icon-houtui:before {
    content: "\e74e";
  }

  .el-icon-qianjin:before {
    content: "\e750";
  }

  .el-icon-playLists:before {
    content: "\e63c";
  }

  .el-icon-laba:before {
    content: "\e643";
  }

  .el-icon-jingyin:before {
    content: "\e606";
  }

  .el-icon-bofang:before {
    content: "\e803";
  }

  .el-icon-yinle:before {
    content: "\e66a";
  }



</style>
