<template>
    <div class="header">
        <div class="header-close">
            <i class="el-icon-minus close-ico"></i>
            <i @click="close1" class="el-icon-full-screen close-ico"></i>
            <el-button @click="close"  type="text" class="close-ico">
                <i class="btn el-icon-close"></i>
            </el-button>
        </div>
    </div>
</template>

<script>
  export default {
    name: 'HeaderBar',
    methods: {
      close () {
        this.$electron.ipcRenderer.send('close')
      },
      close1 () {
        alert(2)
        console.log(22)
      }
    }
  }
</script>

<style scoped lang="scss">
    @import "./node_modules/base_mixins/_base_mixins.scss";
    .header{
        height: 50px;
        @include bgc(#FFB400);
        -webkit-app-region: drag;
    }
    .header-close{
        @include fr;
        @include mar(15 10 0 0);
    }
    .close-ico{
        @include cur;
        @include mar(0 0 0 10);
        -webkit-app-region: no-drag;
    }
</style>
