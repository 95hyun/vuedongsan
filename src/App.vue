<template>

<!--  <ModalComponent :데이터이름="데이터이름"/>-->
<!--  <ModalComponent :작명="원룸들"/>-->
  <ModalComponent @closeModal="모달창열렸니 = false" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>

  <div class="menu">
    <a v-for="menus in 메뉴들" :key="menus">{{ menus }}</a>
  </div>

  <DiscountBanner/>

  <CardComponent @openModalEmit="openModal($event)" v-for ="(원룸들, id) in 원룸들" :key="id" :원룸="원룸들" />
<!--  $event는 자식이 보낸 데이터가 담겨있음-->
<!--  그냥 id 라고해도됨-->
</template>

<script>
import oneroomData from './assets/data/oneroom.js';
import DiscountBanner from "@/DiscountBanner.vue";
import ModalComponent from "@/ModalComponent.vue";
import CardComponent from "@/CardComponent.vue";

export default {
  name: 'App',
  data() {
    return {
      원룸들 : oneroomData,
      메뉴들 : ['Home', 'Shop', 'About'],
      모달창열렸니 : false,
      누른거: null,
    }
  },
  methods: {
    openModal(id) {
      this.모달창열렸니 = true;
      this.누른거 = id;
    },
  },
  components: {
    CardComponent,
    ModalComponent,
    DiscountBanner
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
