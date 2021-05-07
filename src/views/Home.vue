<template>
    <div class="main">
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
      <div @click="openMenu" class="header__menu menu-btn" id="menu-btn">
            <span class="menu-btn__bar"></span>
            <span class="menu-btn__bar"></span>
            <span class="menu-btn__bar"></span>
      </div>
      <div id="menuDiv" class="menu-non">
        <nav class="menu-nav">
          <ul class="menuul">
            <router-link to="/about" ><li class="item">
              <span class="label">故事簡介</span>
              <span class="labelEn">Story</span>
            </li></router-link>
            <li class="item">
              <span class="label">廣播劇聲演</span>
              <span class="labelEn">Voice</span>
            </li>
            <li class="item">
              <span class="label">商品情報</span>
              <span class="labelEn">Product</span>
            </li>
            <li class="item">
              <span class="label">預購活動</span>
              <span class="labelEn">Pre-Sale</span>
            </li>
            <li class="item">
              <span class="label">製作介紹</span>
              <span class="labelEn">Staff</span>
            </li>
          </ul>
        </nav>
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

.menuActive{
 visibility: visible;
}
.menu-non{
 visibility: hidden;
}
#menuDiv{
  background-color:#96514d;
  width:100%;
  height: 100%;
  position:absolute;
  top:0;
  left:0;
  z-index: 9;
  padding-top: 8.69565vw;
}
.menu-nav{
  width: 100%;
  position: fixed;
}
.menuul{
  font-family: 'Noto Serif TC',sans-serif;
  font-weight: 400;
  font-size:1.2em;
  position: relative;
  list-style: none;
  padding: 0px;
}
.menuul li{
  position: relative;
  margin-top: 25px;
  color:#fff;
  transition: color 0.5s ease;
}
.menuul a{ text-decoration:none;}
.menuul li:hover{
  color:#deb068;
}
.menuul .label{
  display: block;
}
.menuul .labelEn{
  display: block;
  font-size:0.6em;
  color:#333;
}
.main {
    position: fixed;
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
.header__menu{
    position: absolute;
    right: 0px;
    top:0px;
    margin:10px;
    z-index: 999;
}
.menu-btn {
    display: inline-block;
    margin-bottom: 4px;
    width: 25px;
    height: 15px;
    z-index: 2;
    cursor: pointer;
    z-index:999;
}
.menu-btn__bar {
    position: absolute;
    display: inline-block;
    width: 100%;
    height: 1px;
    background-color: #fff;
    -webkit-transition-duration: .4s;
    transition-duration: .4s;
}
.menu-btn__bar:first-of-type {
    top: 0;
    left: 0;
    right: 0;
    margin: 0 auto;
    -webkit-transform-origin: left center;
    transform-origin: left center;
}
.menu-btn__bar:nth-of-type(2) {
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
}
.menu-btn__bar:nth-of-type(3) {
    bottom: 0;
    left: 0;
    right: 0;
    margin: 0 auto;
    -webkit-transform-origin: left center;
    transform-origin: left center;
}
.menu-btn.is-menu-active .menu-btn__bar:first-of-type {
    -webkit-transform: rotate(34deg);
    transform: rotate(38deg);
}
.menu-btn.is-menu-active .menu-btn__bar:nth-of-type(2) {
    opacity: 0;
}
.menu-btn.is-menu-active .menu-btn__bar:nth-of-type(3) {
    -webkit-transform: rotate(-34deg);
    transform: rotate(-34deg);
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

