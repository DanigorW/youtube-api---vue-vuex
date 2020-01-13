<template>
  <div class="homePage">
      <SerchBar/>
      <div class="video-container">
        <Video/>
        <VideoList/>

      </div>
      
  </div>
</template>

<script>
import SerchBar from '../components/SerchBar'
import Video from '../components/Video'
import VideoList from '../components/VideoList'

export default {
    name:'homePage',

    components: {
      SerchBar,
      Video,
      VideoList
      
    }
}
</script>

<style>
  .video-container {
    display: flex;
    margin-top: 20px;
    justify-content: space-between;
    flex-wrap: wrap;
  }
</style>