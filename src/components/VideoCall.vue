<template>
  <div class="video-call">
    <div id="video"></div>
    <div v-if="status.video" id="video-small"></div>
    <header class="header">
      <span class="username">someone</span>
    </header>
    <footer class="footer">
      <div class="pannel">
        <div class="pannel__btn">
          <button
            @click="switchVideo"
            class="btn btn__video"
            :class="{ 'btn__video--off': status.video }"
          ></button>
        </div>
        <div class="pannel__btn">
          <button
            @click="switchAudio"
            class="btn btn__audio"
            :class="{ 'btn__audio--off': status.audio }"
          ></button>
        </div>
        <div class="pannel__btn">
          <button @click="endCall" class="btn btn__call"></button>
        </div>
      </div>
    </footer>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";

@Component
export default class VideoCall extends Vue {
  status = {
    video: true,
    audio: true,
  };

  roomId = this.$route.params.roomId;

  switchVideo(): void {
    console.log("video");
    this.status.video = !this.status.video;
  }

  switchAudio(): void {
    console.log("audio");
    this.status.audio = !this.status.audio;
  }

  endCall(): void {
    console.log("and-call");
  }
}
</script>

<style scoped lang="stylus">
.video-call
  height 100%
  position relative
  display flex
  flex-direction column
  justify-content space-between

#video
  position absolute
  top 0
  left 0
  right 0
  bottom 0
  background-color #808080

#video-small
  position absolute
  top 20px
  right 20px
  width 200px
  height 160px
  background-color green

.header
  position relative
  text-align center
  height 130px
  background-image linear-gradient(180deg, rgba(0, 0, 0, 0.86) -3.79%, rgba(0, 0, 0, 0.00208418) 99.99%, rgba(0, 0, 0, 0) 100%);
  padding-top 20px

.username
  font-size 25px
  color #fff

.footer
  position relative
  height 130px
  background-image linear-gradient(360deg, rgba(0, 0, 0, 0.86) 0%, rgba(0, 0, 0, 0.00208418) 99.99%, rgba(0, 0, 0, 0) 100%);
  padding-top 30px

.pannel
  display flex
  justify-content center

.pannel__btn
  margin 0 16px

.btn
  border none
  width 55px
  height 55px
  border-radius 50%
  outline none
  cursor pointer
  background-repeat no-repeat
  background-position center

.btn__video
  background-color #6C6C6C
  background-image url('../assets/video-on.svg')

  &--off
    background-color #D9D9D9
    background-image url('../assets/video-off.svg')

.btn__audio
  background-color #6C6C6C
  background-image url('../assets/mic-on.svg')

  &--off
    background-color #D9D9D9
    background-image url('../assets/mic-off.svg')

.btn__call
  background-color #990000
  background-image url('../assets/end-call.svg')
</style>
