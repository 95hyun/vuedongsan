<template>
  <div>
    <img :src="원룸들.image" alt="room" class="room-img">
<!--    <h4 @click="openModal(id)"> {{ 원룸들.title }}</h4>-->
    <a> {{ 원룸들.price }}원</a>
  </div>
</template>

<script>
export default {
  name : 'CardComponent',
  props : {
    원룸들 : Array,
    openModal : Function,
  },

}
</script>

<style>

</style>