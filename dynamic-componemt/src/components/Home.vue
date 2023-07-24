<template>
    <div>Home component</div>
  </template>
  
  <script>
  export default {
    name: "Home",
    data(){
      return{
  
      }
    },
    unmounted(){
        console.log('home page unmounted')
    },
    activated(){
        console.log('home page activated')
    },
    desactivated(){
        console.log('home page activated')
    }
  };
  </script>
  