<template>
    <div class="play-bar">
        <div class="play-btnMain">
            <i class="element-icons el-icon-houtui play-btnLeft"></i>
            <i class="element-icons el-icon-bofang play-btnPlay play-btn"></i>
            <i class="element-icons el-icon-qianjin play-btnRight"></i>
        </div>
        <div>

        </div>
        <div>

        </div>
        <div>
            <i class="el-icon-laba"></i>
            <el-slider v-model="value1"></el-slider>
            <div>
                随
            </div>
            <span>词</span>
            <span>
                <i class="el-icon-playLists"></i>
            </span>

        </div>

    </div>
</template>

<script>
  export default {
    name: 'PlayBar.vue'
  }
</script>

<style scoped lang="scss">
    .play-bar{
        @include flex;
        @include fixed((b:0,l:0,w:100%,h:48));
        @include bdt(1px solid #e1e1e2);
    }
    .play-btnMain{
        @include pad(7 0 0 30);
        @include fz(0);
        .play-btn{
            @include bgc(#FFB400);
            @include wh(34);
            @include flc(20,34,#ffff);
            @include bdrs(50%);
            @include tac;
            @include cur;
            @include mar(0 24);
            &::before{
                @include c(#fff);
            }
            &:hover{
                @include bgc(lighten(#FFB400,10%));
            }
        }
        .play-btnRight{
            @include wh(30);
            @include flc(16,30,#ffff);
            @include bgc(#FFB400);
            @include bdrs(50%);
            @include tac;
            @include cur;
            &::before{
                @include c(#fff);
            }
            &:hover{
                @include bgc(lighten(#FFB400,10%));
            }
        }
        .play-btnLeft{
            @include wh(30);
            @include flc(16,30,#ffff);
            @include bgc(#FFB400);
            @include bdrs(50%);
            @include tac;
            @include cur;
            &::before{
                @include c(#fff);
            }
            &:hover{
                @include bgc(lighten(#FFB400,10%));
            }
        }
    }
</style>
