<template>


   <Modal :원룸들="원룸들" :누른거="userClick" :모달창="모달창" />

    <div class="menu"> 
      <a v-for="a in navMenu" :key="a"> {{ a }} </a>
    </div>

    <Discount />

    <Card :원룸="원룸들[i]" v-for="(a,i) in 원룸들" :key="a"/>
    <!-- <Card :원룸="원룸들[1]"/>
    <Card :원룸="원룸들[2]"/>
    <Card :원룸="원룸들[3]"/>
    <Card :원룸="원룸들[4]"/>
    <Card :원룸="원룸들[5]"/> -->

    <!-- <div v-for="(a,i) in 원룸들" :key="i">
      <img :src="a.image" class="room-img">
      <h4 @click="모달창 = true; userClick = i">{{a.title}}</h4>
      <p>{{a.price}}원</p>
    </div> -->

</template>

<script>

import data from './assets/oneroom.js'
import Discount from './Discount.vue'
import Modal from './Modal.vue'
import Card from './Card.vue'

export default {
  name: 'App',
  data(){
    return {
      userClick : 0,
      원룸들 : data,
      모달창 : false,
      navMenu : ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0,0,0],
     }
  },

  methods: {
  },

  components: {
    Discount : Discount,
    Modal : Modal,
    Card : Card,
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

.discount {
  background: #eee;
  border-radius: 5px;
  padding: 10px;
  margin: 10px;
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
