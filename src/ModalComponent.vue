<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" alt="room" class="room-img"/>
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
<!--      <input @input="month = $event.target.value">-->
      <input v-model="month">
<!--      <input type="range" min="0" max="12" v-model="month"/>-->
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
  watch : { // 데이터 감시하려면
    month(a) { // 감시하고 싶은 데이터명으로 함수를 만들면 자동으로 감시 지정
      if (isNaN(a)) {
        alert('문자 입력하지마셈')
        this.month = 1;
      }
    },
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