<template>
  <div class="conference">
    <VideoCall />
  </div>
</template>

<script>
import VideoCall from "@/components/VideoCall.vue";

export default {
  name: "Conference",
  components: {
    VideoCall,
  },
};
</script>
<style lang="stylus">
.conference
  height 100%
</style>
