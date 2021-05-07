<template>
    <div class="main">
      <div class="title bb">
      故事簡介 Story
      <hr width=80% size=0.5>
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
<style >
 .bb{font-weight: bold;}
</style>