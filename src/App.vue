<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[selectedRoomId].image" alt="room" class="room-img"/>
      <h4>{{ 원룸들[selectedRoomId].title }}</h4>
      <p>{{ 원룸들[selectedRoomId].content }}</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>
<!--  동적인 UI 만드는 법 :-->
<!--  1. UI의 현재 상태를 데이터로 저장해둠-->
<!--  2. 데이터에 따라 UI가 어떻게 보일지 작성-->

  <div class="menu">
    <a v-for="menus in 메뉴들" :key="menus">{{ menus }}</a>
  </div>

  <div v-for="(원룸들, id) in 원룸들" :key="id">
    <img :src="원룸들.image" alt="room" class="room-img">
    <h4 @click="openModal(id)"> {{ 원룸들.title }}</h4>
    <a> {{ 원룸들.price }} 만원</a>
<!--    <button @click="increase(i)">허위매물신고</button> <span> 신고수 : {{ rooms.신고수 }}</span>-->
  </div>

</template>

<script>
import oneroomData from './assets/data/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      원룸들 : oneroomData,
      메뉴들 : ['Home', 'Shop', 'About'],
      모달창열렸니 : false,
      selectedRoomId: [],
    }
  },
  methods: {
    openModal(id) {
      this.모달창열렸니 = true;
      this.selectedRoomId = id;
    },
  },
  components: {

  },
}
</script>

<style>
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;

}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;

}
</style>
