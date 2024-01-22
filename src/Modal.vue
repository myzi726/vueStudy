<template>
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <Discount />
      <h4>{{원룸들[userClick].title}}</h4>
      <p>{{원룸들[userClick].content}}</p>
      <button @click="modal = false">닫기</button>
    </div>
  </div>
</template>

<script>
    import data from './assets/oneroom.js'
    import Discount from './Discount.vue'

export default {
    name : 'Modal',
    data(){
        return{
            userClick : 0,
            원룸들 : data,
            modal : false,
            navMenu : ['Home', 'Shop', 'About'],
            products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
            신고수 : [0,0,0],
        }
    },

  components: {
    Discount : Discount,
  }
}

</script>

<style>

</style>