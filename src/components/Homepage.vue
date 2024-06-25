<script setup>
import {ref, onMounted, onUpdated} from "vue";
  const title = ref("雪 雁 的 小 窝");
  const description = ref("你好呀，这里是雪雁！")
  const windowWidth =ref(0);
  const windowHeight = ref(0);
  const leftDistance = ref(0);
  const name = ref("雪雁");
  const name2 = ref("@Eleanor1018");
  const description2 = ref("等待与希望");

  onMounted(()=>{
    getWindowResize();
    window.addEventListener('resize',getWindowResize)
  })

  const getWindowResize = function (){
    windowWidth.value = window.innerWidth;
    windowHeight.value = window.innerHeight;
    leftDistance.value = window.innerWidth*0.5 - 50;
  }

  function skip_github(){
    window.open('https://github.com/Eleanor1018');
  }

  function skip_mail(){
    window.open('mailto:EleanorAnatidae@outlook.com');
  }

  function skip_twi(){
    window.open('https://github.com/Eleanor1018')
  }

  function skip_tele(){
    window.open ('https://github.com/Eleanor1018')
  }

  const pages = ref(0);
  const go_into = () => {
    pages.value = 1;
  };

    // const profilePhoto = ref('profile_photo0');
    //
    // if(pages.value === 1){
    //   profilePhoto.value = 'profile_photo1';
    // }
  // const go_into = function (){
  //   pages.value = 1;
  // }
  const profileClass = ref('makecolorpink');
  const articlesClass = ref('makecolorblack');
  const cookClass = ref('makecolorblack');
  const contactmeClass = ref('makecolorblack');
  const select = ref(0);
  const profile = () => {
    select.value = 0;
    profileClass.value = 'makecolorpink';
    articlesClass.value = 'makecolorblack';
    cookClass.value = 'makecolorblack';
    contactmeClass.value = 'makecolorblack';
  }
  const articles = () => {
    select.value = 1;
    profileClass.value = 'makecolorblack';
    articlesClass.value = 'makecolorpink';
    cookClass.value = 'makecolorblack';
    contactmeClass.value = 'makecolorblack';
  }

  const cook = () => {
    select.value = 2
    profileClass.value = 'makecolorblack';
    articlesClass.value = 'makecolorblack';
    cookClass.value = 'makecolorpink';
    contactmeClass.value = 'makecolorblack';
  }

  const contactme = () =>{
    select.value = 3
    profileClass.value = 'makecolorblack';
    articlesClass.value = 'makecolorblack';
    cookClass.value = 'makecolorblack';
    contactmeClass.value = 'makecolorpink';
  }


</script>

<template>
  <div class="main">
    <div class="background">
      <img src="../components/images/a.jpg"/>
    </div>
    <div v-if="pages===0" class="profile_photo">
      <img src="../components/images/image3.jpg"/>
    </div>
    <div v-if="pages === 0" class="introduction">
      <div class="title">
        {{title}}
      </div>
      <div class="description">
        {{description}}
      </div>
      <div class="click_links">
      <ul class="list1">
        <li @click="skip_github">
          <img src="../components/images/github-mark.png" style="width: 2vw ;height: 2vw; border-radius: 50%">
        </li>
        <li @click="skip_mail">
          <img src="../components/images/mail.png" style="width: 2vw ;height: 2vw; border-radius: 50%">
        </li>
        <li @click="skip_twi">
          <img src="../components/images/twitter.png" style="width: 2vw ;height: 2vw; border-radius: 50%">
        </li>
        <li @click="skip_tele">
          <img src="../components/images/telegram.png" style="width: 2vw ;height: 2vw; border-radius: 50%">
        </li>
      </ul>
      </div>
      <div class="go_into" @click="go_into">
        <div class="go_into_title">钻进小窝里</div>
        <img src="../components/images/arrowdown.svg"/>
      </div>
    </div>

    <div v-if="pages === 1" class="background2">
      <div class="leftlist">
        <div class="profile_photo2">
          <img src="../components/images/image3.jpg"/>
        </div>
        <div class="leftlist_name">{{name}}</div>
        <div class="leftlist_name2">{{name2}}</div>
        <div class="leftlist_desc">{{description2}}</div>
        <div class="leftlist2">
          <hr class="leftlist_line">
          <div @click="profile" :class="profileClass">
            <span class="leftlist_text">个人简介</span>
          </div>
          <hr class="leftlist_line">
          <div @click="articles" :class="articlesClass">
            <span class="leftlist_text">文章</span>
          </div>
          <hr class="leftlist_line">
          <div @click="cook" :class="cookClass">
            <span class="leftlist_text">小厨娘空间</span>
          </div>
          <hr class="leftlist_line">
          <div @click="contactme" :class="contactmeClass">
            <span class="leftlist_text">联系方式</span>
          </div>
          <hr class="leftlist_line">
        </div>
      </div>
      <div class="content">
        <div v-if="select === 0">
          <div class="content_title">
            个人简介
          </div>
          <hr class="leftlist_line">
          <div class="content0">
            你好呀，这里是雪雁！
            <br>
            我本是雁形目鸭科雁属的一种鸟，因为误打误撞，服用了化形为人的仙草而变成了人形。
            <br>
            身为一只雪雁，化为人形时，虽然暂时失去了翅膀，但仍然向往着自由和天空。
            <br>
            终有一天我会找回自己的身体，翱翔九天，无拘无束~
            <br>
            欢迎来到我的小窝。叫我雪雁就好，当然，你也可以叫我雪雪，雁雁，或者随你喜欢，只要是可爱的名字就好~
            <br>
            祝看到这段文字的小可爱们健康快乐~
          </div>
        </div>
        <div v-if="select === 1">
          <div class="content_title">
            文章
          </div>
          <hr class="leftlist_line">
        </div>
        <div v-if="select === 2">
          <div class="content_title">
            小厨娘空间
          </div>
          <hr class="leftlist_line">
        </div>
        <div v-if="select === 3">
          <div class="content_title">
            联系方式
          </div>
          <hr class="leftlist_line">
        </div>

      </div>
    </div>
  </div>

</template>

<style scoped>
.main{
  width: 100%;
  height: 100%;
  padding: 0;
  margin: 0;
}
.background{
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}
.background img{
  max-width: 100%;
  height: v-bind('windowHeight');
  z-index: 1;
}
.background2{
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}
.introduction{
  position: relative;
  text-align: center;
  width: 80%;
  //height: 100vh;
  height: inherit;
  margin: auto;
  background-color: white;
  opacity: 0.8;
  z-index: 2;
}
.profile_photo{
  position: absolute;
  height: 20vh;
  width: 20vh;
  margin-left: auto;
  margin-right: auto;
  padding: 10vh 0 10vh 0;
  z-index: 3;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.profile_photo img{
  width: 100%;
  height: 100%;
  margin: auto;
  border-radius: 50%;
}
.leftlist{
  z-index: 2;
  position: relative;
  width: 25vw;
  height: inherit;
  margin: 5vh 5vw;
  background-color: white;
  opacity: 0.9;
  text-align: center;
}
.profile_photo2{
  position: relative;
  height: 15vh;
  width: 15vh;
  margin: 0 auto;
  padding-top: 10vh;
  z-index: 3;
}
.leftlist_name{
  padding-top: 2vh;
  font-size: 40px;
  font-weight: bold;
  color: hotpink;
  font-family: KaiTi;
}
.leftlist_name2{
  padding-top: 0.5vh;
  font-size: 28px;
  font-weight: bold;
  color: blue;
  font-family: Arial;
}
.leftlist_desc{
  font-family:KaiTi ;
  font-size: 28px;
  color: hotpink;
  padding-top: 2vh;
  padding-bottom: 3vh;
}
.makecolorblack{
  color:black;
  font-weight: normal;
  padding-bottom: 0.3vh;
  padding-top: 0.3vh;
}
.makecolorpink{
  color:hotpink;
  font-weight: bold;
  padding-bottom: 0.3vh;
  padding-top: 0.3vh;
}
.leftlist_text{
  font-size: 26px;
  font-family:KaiTi ;
}
.content{
  width: 65vw;
  z-index: 2;
  position: relative;
  height: inherit;
  margin: 5vh 5vw 5vh 0;
  background-color: white;
  opacity: 0.9;
}
.content_title{
  font-size: 40px;
  font-weight: bold;
  color: hotpink;
  font-family: KaiTi;
  padding: 3vh 0 0 2vw;
}
.profile_photo2 img{
  width: 100%;
  height: 100%;
  margin: auto;
}
.title{
  padding-top: 35vh;
  font-size: 60px;
  color: blue;
  font-weight: bold;
  font-family: Arial;
}
.description{
  padding-top: 5vh;
  color: hotpink;
  font-size: 26px;
  font-family: Calibri;
}
.click_links{
  display: inline;
  list-style: none;
  margin: auto;
  padding: 0 5vh 0 5vh;
}
.list1{
  margin: 0;
  padding: 0;
}
.list1 li{
  display: inline;
  padding:  0 1vw 0 1vw;
}
.bottom{
  position: relative;
  margin-top: auto;
  padding: 0;
}
.go_into{
  position: fixed;
  z-index: 4;
  bottom: 0;
  right: 0;
  left: 0;
  margin-top: 10vh;
}
.go_into_title{
  font-size: 24px;
  font-family: Calibri;
  color: hotpink;
}
.go_into img{
  width: 10vh;
  height: 10vh;
}
.content0{
  font-size: 26px;
  font-family: Calibri;
  padding-left: 2vw;
  padding-right: 2vw;
}


</style>