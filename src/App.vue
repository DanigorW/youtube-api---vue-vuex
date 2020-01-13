<template>
  <div id="app">
    <Navbar/>
 <div class="container">
    <router-view/>
    
 </div>
  </div>
</template>

<script>
import Navbar from '../src/components/Navbar'
export default {
  name:'app',

   components: {
      Navbar
    }


}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');
body {
  font-family: 'Roboto', sans-serif;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}


.container {
  max-width: 1170px;
  width: 100%;
  margin: 0 auto;
}

button {
  cursor: pointer;
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
}

</style>