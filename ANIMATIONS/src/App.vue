<template>
  <button @click="changeFlag" type="button">Toggle</button>
<!--   <transition name="fade" mode="out-in">
    <p v-if="flag" key="mmmmain" :style="[{ display: 'block', width: '100% !important' }]">
      Hello vue community
    </p>
    <p v-else   key="kkkk" :style="[{ display: 'block', width: '100% !important' }]">
      Hello vue community
    </p>
  </transition> -->

  <transition type="animation" appear name="zoom">
    <h2 v-show="flag">Hello</h2>
  </transition>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      flag: true,
    };
  },
  methods: {
    changeFlag() {
      this.flag = !this.flag;
    },
  },
};
</script>

<style>
/* .fade-enter-from {
  opacity: 0;
}
.fade-enter-active{
  transition: all 0.3s linear;
}


.fade-leave-active{
  transition: all 0.3s linear;
}

.fade-leave-to{
  opacity: 0;
} */

.zoom-enter-active{
  animation: zoom-in 1s ease-in-out;
  transition: all 1s linear;
}
.zoom-leave-active{
  animation: zoom-out 1s ease-in-out;
  transition: all 1s linear;


}

.zoom-enter-from{
  opacity: 0;
  
}

.zoom-leave-to{
  opacity: 0;
}
@keyframes zoom-in {
  0%{
    transform: scale(0,0);
  }

  100%{
    transform: scale(1,1);
  }
}

@keyframes zoom-out {
  0%{
    transform: scale(1,1);
    
  }

  100%{
    transform: scale(0,0);
  }
}
</style>
