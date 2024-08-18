<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" alt="room" class="room-img"/>
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
<!--      <input @input="month = $event.target.value">-->
<!--      <input v-model="month">-->
      <select v-model="month">
        <option value="1">1개월</option>
        <option value="2">2개월</option>
        <option value="3">3개월</option>
        <option value="4">4개월</option>
        <option value="5">5개월</option>
        <option value="6">6개월</option>
        <option value="7">7개월</option>
        <option value="8">8개월</option>
        <option value="9">9개월</option>
        <option value="10">10개월</option>
        <option value="11">11개월</option>
        <option value="12">12개월</option>
      </select>
<!--      사용자가 <input> 에 입력한 것은 전부 문자 자료형!-->
<!--      곱셈은 잘 될 수 있으니, 덧셈하는 순간 문자열 덧셈이 되어버림-->
<!--      <input v-model.number="month"/> 이렇게 해야 number 타입으로 지정-->
      <p> {{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }} 원</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name : 'ModalComponent',
  data() {
    return {
      month : 1,
    }
  },
  props : { // props 는 readOnly !!
    원룸들 : Array,
    누른거: Number,
    모달창열렸니: Boolean,
  },
}

</script>

<style>

</style>