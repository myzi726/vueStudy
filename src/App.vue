<template>

 <!-- 상세페이지 모달창 -->
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modal = false">닫기</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="a in navMenu" :key="a"> {{ a }} </a>
  </div>


  <div v-for="i in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4>{{원룸들[i].title}}</h4>
    <p>{{원룸들[i].price}}</p>
  </div>

</template>

<script>

import data from './assets/oneroom.js'


export default {
  name: 'App',
  data(){
    return {
      원룸들 : data,
      modal : false,
      navMenu : ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0,0,0],
     }
  },

  methods: {
    // increase() {
    //   this.신고수 += 1;
    // }
  },

  components: {
  }
}
</script>

<style>
body {
  margin : 0
}

div {
  box-sizing : border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
   border-radius: 8px;
   padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img{
  width: 100%;
  margin-top: 40px;
}
</style>
