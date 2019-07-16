<template>
    <div class="header">
        <span class="logo">
            FuseMusic
        </span>
        <div class="header-close">
            <i class="el-icon-minus close-ico" @click="minimize"></i>
            <i @click="close1" class="el-icon-full-screen close-ico"></i>
            <el-button @click="close"  type="text" class="close-ico">
                <i class="btn el-icon-close"></i>
            </el-button>
        </div>
    </div>
</template>

<script>
  import { ipcRenderer } from 'electron'
  export default {
    name: 'HeaderBar',
    methods: {
      close () {
        ipcRenderer.send('asynchronous-message', 'ping')

        console.log(1)
      },
      minimize () {
        ipcRenderer.send('min')
        console.log(33)
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
    .logo{
        @include pad(0 0 0 20);
        @include flc(20,50,#fff);
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
