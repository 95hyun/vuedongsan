<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" alt="room" class="room-img"/>
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].price }}원</p>
      <p>{{ 원룸들[누른거].content }}</p>
<!--      <button @click="모달창열렸니 = false">닫기</button>-->
    </div>
  </div>
</template>

<script>
export default {
  name : 'ModalComponent',
  props : { // props 는 readOnly !!
    원룸들 : Array,
    누른거: Number,
    모달창열렸니 : Boolean,
  }

}

</script>

<style>

</style>