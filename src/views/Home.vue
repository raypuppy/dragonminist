<template>
    <div class="main">
      <div class="TopContent">
      <div class="title shining">
          風<br>流<br>宰<br>相<br>臥<br>龍<br>床
      </div>
      <div class="display">
        <p>ami亞海</p><p>．</p>
        <p class="alt">聲音無限廣播劇團</p><p>．</p>
        <p>陌上商行</p><p>．</p>
        <p class="alt">廣播劇</p>
        <p class="alt">Coming Soon</p>
      </div>
     </div>
  </div>
</template>

<script>
import $ from 'jquery'
export default {
  data(){
    return{

    }
  },
  methods: {
    openMenu () {
       $('.transform').toggleClass('menuActive');
       if($(".menu-btn").hasClass("is-menu-active")){
         $(".menu-btn").removeClass("is-menu-active");
         $("#menuDiv").removeClass('menuActive');
         $("#menuDiv").addClass('menu-non');
      }else{
         $(".menu-btn").addClass("is-menu-active");

         $("#menuDiv").addClass('menuActive');
         $("#menuDiv").removeClass('menu-non');
      }
    },
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@200;400;900&display=swap');

.TopContent{
   top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    z-index: -999;
    background-image: url('~@/assets/bg2.jpg');
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-position: center;
    background-size: cover;
    justify-content: center;
    align-items: center;
    text-align: center;
    display: flex;
    height: 100vh;
}
.title{
  color:#fff;
  font-family: 'Noto Serif TC', serif;
}
.display{
  font-family: 'Noto Serif TC',sans-serif;
  font-weight: 400;
  color:#deb068;
  animation: display 5s linear ;
  animation-delay: 3s;
  opacity: 0;
  -webkit-animation-fill-mode:forwards;  /* 確保在動畫完成後，我們會保持在最後的 keyframe 值 (opacity: 1)*/
 -moz-animation-fill-mode:forwards;
 animation-fill-mode:forwards;
 font-size:1em;
}
.display .alt{
  color:#fff;
}
@keyframes display {
  from {
    opacity:0;
  }
  to {
     opacity:1;
  }
}
.shining {
  padding: 7px;
  border-right: 1px #fff solid;
  margin: 9px;
  font-size: 2.5em;
  font-family: 'Noto Serif TC', serif;
  font-weight: 900   ;
  letter-spacing: 4px;
  text-transform: uppercase;
  background: linear-gradient(180deg, rgba(255,255,255,1) 0%, rgba(0,0,0,0) 50%, rgba(255,255,255,1) 100%);
  background-size: 1500px 1500px;
  background-repeat: repeat;
  color: transparent;
  background-clip: text;
  -webkit-background-clip: text;
   animation: shining 3s linear ;
   animation-delay: 1s;
}

@keyframes shining {
  from {
    background-position:  top -1000px right 0px;

  }
  to {
    background-position:  top 100px right  0px;
  }
}
</style>

