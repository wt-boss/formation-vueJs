
<script>
import About from './components/About.vue';
import Home from './components/Home.vue';
  export default {
    name:"app",
    data(){
      return{
        componentName:"Home"
      }
      
    }
    
  }
</script>
<template>

  <select name="" id="" v-model="componentName">
    <option value="Home">Home</option>
    <option value="About">About</option>
  </select>
  <div>
    <KeepAlive>
      <component :is="componentName"></component>
    </KeepAlive>
   
  </div>
</template>



