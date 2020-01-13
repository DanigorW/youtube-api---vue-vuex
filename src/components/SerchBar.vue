<template>
  <div class="serch-bar">
     <div class="input-serch">
       <form @submit.prevent="onSubmit"> 
         <div v-if="showError" class="error">
           <span>please fill out the field below</span>
         </div>
          <input type="text" v-model="inputValue" placeholder="Search...">
          <button @click="showErrorFunc">Search</button>
       </form>
         
        
     </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
    name:'SearchBar',

    data(){
      return{
        apiKey:'AIzaSyBWmuNwI5LO4w2ILCJ8llRqMR87DLMSRLk',
        googleUrl: 'https://www.googleapis.com/youtube/v3/search',


        inputValue: null,    
        showError: false,
      }
    },

    methods: {
     async onSubmit(){
        const data = await axios.get('https://www.googleapis.com/youtube/v3/search', {
          params: {
            key: this.apiKey,
            type:'video',
            part: 'snippet',
            maxResults: 10,
            q:this.inputValue,

          },  
        })
        
         this.$store.state.dataFromApi = data.data.items;
      },

      showErrorFunc(){
      if(this.inputValue === null){
        this.showError = true;
        setTimeout(() => {
        this.showError = false;
        }, 3000)
      }
    }
    },

    

    
}
</script>

<style>
  

  .input-serch input {
    width: 80%;
    height: 40px;
    padding: 0 10px;
    margin-top: 20px;
    font-size: 22px;
    
  }

  .input-serch button {
    height: 40px;
    outline: none;
    border: none;
    width: 20%;
    font-size: 22px;
    transition: all .5s;
    background: crimson;
    color: #fff;
  }

  .input-serch button:hover {
      background: rgb(255, 0, 51);
  }

  .error {
    margin-top: 20px;
    color: red;
    text-transform: uppercase;

  }
</style>