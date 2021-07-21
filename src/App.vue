<template>
  <div id="app" class="main">
     <div @click="openMenu" class="header__menu menu-btn" id="menu-btn">
            <span class="menu-btn__bar"></span>
            <span class="menu-btn__bar"></span>
            <span class="menu-btn__bar"></span>
      </div>
     <div id="menuDiv" class="menu-non">
        <nav class="menu-nav" >
          <ul class="menuul">
            <router-link to="/about" ><li @click="openMenu" class="item">
              <span class="label">故事簡介</span>
              <span class="labelEn">Story</span>
            </li></router-link>
            <router-link to="/voice" ><li @click="openMenu" class="item"> 
              <span class="label">廣播劇聲演</span>
              <span class="labelEn">Voice</span>
            </li></router-link>
            <router-link to="/product" ><li class="item" @click="openMenu">
              <span class="label">商品情報</span>
              <span class="labelEn">Product</span>
            </li></router-link>
             <router-link to="/presale" > <li class="item" @click="openMenu">
              <span class="label">預購活動</span>
              <span class="labelEn">Pre-Sale</span>
            </li></router-link>
             <router-link to="/staff" ><li class="item" @click="openMenu">
              <span class="label">製作介紹</span>
              <span class="labelEn">Staff</span>
            </li></router-link>
          </ul>
        </nav>
      </div>
      <router-view/>
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
       console.log(document.body.clientWidth);
       $('.transform').toggleClass('menuActive');
       if($(".menu-btn").hasClass("is-menu-active")){
         $(".menu-btn").removeClass("is-menu-active");
         $("#menuDiv").removeClass('menuActive');
         if(document.body.clientWidth<600){
            $("#menuDiv").addClass('menu-non');
          }
      }else{
         $(".menu-btn").addClass("is-menu-active");
         $("#menuDiv").addClass('menuActive');
          if(document.body.clientWidth<600){
            $("#menuDiv").removeClass('menu-non');
          }
      }
     
    },
    
  }
}
</script>
<style >
html {
            height: 100%;
        }

 body {
            background-image: url('~@/assets/bg2.jpg');
            background-repeat: no-repeat;
            background-attachment: fixed;
            background-position: center;
            background-size: cover;
}
.menuActive{
 visibility: visible;
}

#menuDiv{
  background-color:#96514d;
  width:100%;
  height: 10%;
  position:fixed;
  top:0;
  right:0;
  z-index: 9;
}

.menu-nav{
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
}
.menuul{
  font-family: 'Noto Serif TC',sans-serif;
  font-weight: 400;
  font-size:1.2em;
  display: flex;
  list-style: none;
  padding: 0px;
}
.menuul li{
  margin-left:30px;
  color:#fff;
  transition: color 0.5s ease;
  position: relative;
}
.menuul li:hover::before{
  content: '閱';
  color:brown;
  font-size:30px;
  font-weight: 400;
  position: absolute;
  left:0;
  background-color: rgba(255,255,255,.2);
  border: 4px solid brown;
  box-shadow: 1px 1px 10px #333;
  border-radius: 50%;
  transform:translateX(-80%) rotate(-45deg)
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
    z-index: -999;
    width: 100%;
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
    visibility: hidden;
    position:absolute;
    top:0px;
    right:0px;
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
    transform: rotate(34deg);
}
.menu-btn.is-menu-active .menu-btn__bar:nth-of-type(2) {
    opacity: 0;
}
.menu-btn.is-menu-active .menu-btn__bar:nth-of-type(3) {
    -webkit-transform: rotate(-34deg);
    transform: rotate(-34deg);
}
 .bb{font-weight: bold;}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
@media  (max-width: 600px)  {
  .menu-btn{visibility:visible;}
   #menuDiv{width:100%;}
  .menu-nav{width: 100%;}
  .menu-non{
  visibility: hidden;
  }

  #menuDiv{
    height: 100%;
    position:absolute;
    top:0;
    right:0;
    z-index: 9;
    padding-top: 8.69565vw;
  }
  .menuul{
    width: 100%;
    display: flex;
    flex-direction:column;
    justify-content:center;
    align-content: center;
  }
  .menuul li{
    margin-top: 50px;
  }
}
</style>
