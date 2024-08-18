<template>

  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>{{ rooms[selectedRoomId].modalTitle }}</h4>
      <p>{{ rooms[selectedRoomId].modalDetail }}</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>
<!--  동적인 UI 만드는 법 :-->
<!--  1. UI의 현재 상태를 데이터로 저장해둠-->
<!--  2. 데이터에 따라 UI가 어떻게 보일지 작성-->

  <div class="menu">
    <a v-for="menus in 메뉴들" :key="menus">{{ menus }}</a>
  </div>

  <div v-for="(rooms, id) in rooms" :key="id">
    <img :src="rooms.img" alt="room" class="room-img">
    <h4 @click="openModal(id)"> {{ rooms.product }}</h4>
    <a> {{ rooms.price }} 만원</a>
    <button @click="increase(i)">허위매물신고</button> <span> 신고수 : {{ rooms.신고수 }}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      rooms : [
        { id: 0,
          product: '역삼동원룸',
          price: 70,
          신고수: 0,
          img: require('./assets/room0.jpg'),
          modalTitle: '역삼동원룸 제목',
          modalDetail: '역삼동원룸 자세한 설명'},
        { id: 1,
          product: '천호동원룸',
          price: 60,
          신고수: 0,
          img: require('./assets/room1.jpg'),
          modalTitle: '천호동원룸 제목',
          modalDetail: '천호동원룸 자세한 설명'},
        { id: 2,
          product: '마포구원룸',
          price: 50,
          신고수: 0,
          img: require('./assets/room2.jpg'),
          modalTitle: '마포구원룸 제목',
          modalDetail: '마포구원룸 자세한 설명'},
      ],
      메뉴들 : ['Home', 'Shop', 'About'],
      모달창열렸니 : false,
      selectedRoomId: [],
    }
  },
  methods: {
    increase(i) {
      this.rooms[i].신고수 += 1;
    },
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
