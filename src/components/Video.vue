<template>
  <div class="video">
      <div  class="video-layout">
          <iframe  :src="videoSelectedId"  width="560" height="315"  frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>


      <div class="video-info">
          
          <div v-if="videoSelected">
              <h3>{{videoSelected.snippet.title}}</h3>
              <p>{{videoSelected.snippet.description}}</p>
          </div>

          <span v-else>more info...</span>

       
        
      </div>
  </div>
</template>

<script>
export default {
 name: 'Video',

 computed: {
     videoSelected(){
      return this.$store.state.itemClicked
     },
     
     videoSelectedId(){
         if(this.$store.state.itemClicked){
              let videoId = this.$store.state.itemClicked.id.videoId;
              return `https://www.youtube.com/embed/${videoId}`
         }

         return null
       
      
     }
 },
}
</script>

<style>
    .video-layout {
        border: 2px solid #eee;
        width: 800px;
        height: 500px;
    }

    .video-info {
        margin-top: 10px;
        background: rgb(221, 221, 221);
        width: 800px;
        height: 100px;
        padding: 10px;
        display: flex; 
        align-items: center;
    }

    .video-layout iframe {
        width: 100%;
        height: 100%;
    }
</style>