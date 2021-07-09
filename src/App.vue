<template>
  <div id="app" class="main">
  
     <div @click="openMenu" class="header__menu menu-btn" id="menu-btn">
            <span class="menu-btn__bar"></span>
            <span class="menu-btn__bar"></span>
            <span class="menu-btn__bar"></span>
      </div>
     <div id="menuDiv" class="menu-non">
        <nav class="menu-nav">
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
<style >
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
</style>
