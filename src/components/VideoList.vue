<template>
  <div class="VideoList">
    
      <ul >
        <li v-for="(item, index) in dataFromState" :key="index" @click="onClick(item,index)">
            <div class="video-item">
                <img :src="item.snippet.thumbnails.default.url" alt="image">
                <span>{{item.snippet.title}}</span>
            </div>
            
        </li>
      </ul>
  </div>
</template>

<script>

export default {
 name: 'VideoList',

 methods: {
     onClick(index){
         this.$store.state.itemClicked = index;
     },
     
 },

computed: {
    dataFromState(){
        return this.$store.state.dataFromApi
    },
    
},


}


</script>

<style>
    .VideoList {
        padding: 20px;
        width: 350px;
        height: 610px;
        border: 2px solid #eee;
        
        overflow-y: scroll;
        
    }

    .VideoList ul {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    .video-item {
        border: 2px solid #eee;
        display: flex;
        align-items: center;
        margin: 10px 0;
       
    }

    .video-item img {
        margin-right: 10px;
    }

    .video-item span {
        font-size: 14px;
    }

    .video-item {
        transition: all .5s;
        cursor: pointer;
    }
    .video-item:hover {
        background: rgb(228, 228, 228)
    }




</style>