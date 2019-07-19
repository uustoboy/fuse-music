<template>
    <div class="play-bar">
        <div class="play-btnMain">
            <i class="element-icons el-icon-houtui play-btnLeft"></i>
            <i class="element-icons el-icon-bofang play-btnPlay play-btn"></i>
            <i class="element-icons el-icon-qianjin play-btnRight"></i>
        </div>
        <div class="play-song">
            <span class="play-songLeftTime">01:32</span>
            <span class="play-songRightTime">01:32</span>
            <el-slider v-model="songTime" :input-size="mini" ></el-slider>
        </div>
        <div class="play-right">
            <i :class="volume==0?'el-icon-jingyin':'el-icon-laba'"></i>
            <span class="volume-slider">
                <el-slider v-model="volume" :input-size="mini" @change="changeVolume"></el-slider>
            </span>
            <div class="play-mode" @click="changeMode">
                {{mode[modeIndex]}}
            </div>
            <div class="play-lyric">词</div>
            <div class="song-list">
                <span class="song-listInfo" @click="changeListShow">
                    <i class="el-icon-playLists el-icon-playListsIco"></i>
                    <span class="song-listNum">0</span>
                </span>
            </div>
            <div class="song-listMain" v-show="songListShow">

            </div>
        </div>

    </div>
</template>

<script>
  export default {
    name: 'PlayBar.vue',
    data () {
      return {
        songTime: 0,
        volume: 50,
        mode: ['随', '单', '循'],
        modeIndex: 0,
        songListShow: false
      }
    },
    methods: {
      changeVolume () {

      },
      changeMode () {
        this.modeIndex = (this.modeIndex + 1) % this.mode.length
      },
      changeListShow () {
        this.songListShow = !this.songListShow
      }
    }
  }
</script>

<style scoped lang="scss">
    .play-bar{
        @include flex;
        @include fixed((b:0,l:0,w:100%,h:48));
        @include bdt(1px solid #e1e1e2);
        @include jc(space-between);
    }
    .play-btnMain{
        @include pad(7 0 0 30);
        @include fz(0);
    }
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
    .play-lyric{
        @include wh(14);
        @include bd(1 solid #919192);
        @include flc(12,14,#666);
        @include tac;
        @include mar(0 19);
    }
    .play-right{
        @include rel;
        @include flex;
        @include pad(0 14 0 0);
        @include ai(center);
    }
    .song-list{
        @include rel;
    }
    .song-listMain{
        @include abs((r:0,b:49,w:578,h:470));
        @include bgc(#fafafa);

    }
    .song-listInfo{
        @include f(0);
        @include cur;
    }
    .el-icon-playListsIco{
        @include fz(16);
        @include vic;
        @include mar(0 -2 0 0);
    }
    .song-listNum{
        @include inblock;
        @include wh(30,14);
        @include flc(10,14,#333);
        @include tac;
        @include bdrs(0 14 14 0);
        @include bgc(#e1e1e2);
        @include vic;
    }
    .play-mode{
        @include wh(14);
        @include flc(12,14,#666);
        @include tac;
        @include mar(0 19);
        @include cur;
    }
    .volume-slider{
        @include inblock;
        @include w(100);
        @include mar(0 0 0 15);
    }
    .play-song{
        @include rel;
        @include fx(1);
        @include mar(0 70);
        @include ai(center);
    }
    .play-songLeftTime{
        @include abs((l:-50,b:50%));
        @include flc(12,16,#333);
        @include mar(-16/2 0 0 0);
    }
    .play-songRightTime{
        @include abs((r:-50,b:50%));
        @include flc(12,16,#333);
        @include mar(-16/2 0 0 0);
    }
</style>
