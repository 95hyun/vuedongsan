<template>
  <div>
    <img :src="원룸.image" alt="room" class="room-img">
    <h4 @click="openModalEmit"> {{ 원룸.title }}</h4>
    <a> {{ 원룸.price }}원</a>
  </div>
</template>

<script>
export default {
  name : 'CardComponent',
  props : {
    원룸 : Object,
  },
  methods : {
    openModalEmit() {
      this.$emit('openModalEmit', this.원룸.id)
    },
  }
}
</script>

<style>

</style>