<template>
  <div class="black-bg" v-if="모달창 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" style="width: 100%">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <input @input="month = $event.target.value">
      <!-- input 이벤트 간략하게 : v-model="month" -->
      <p> {{month}}개월 선택함<br/>{{ 원룸들[누른거].price * month }}원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>

  export default {
      name : 'Modal',
      data() {
        return {
          month : 1,
        }
      },
      props : {
        원룸들 : Array,
        누른거 : Number,
        모달창 : Boolean,
      },
  }

</script>

<style>

</style>