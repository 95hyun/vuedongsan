<template>
  <div class="menu">
    <a v-for="menus in 메뉴들" :key="menus">{{ menus }}</a>
  </div>

  <div v-for="(rooms, i) in rooms" :key="i">
    <h4> {{ rooms.product }}</h4>
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
        { product: '역삼동원룸', price: 70, 신고수: 0},
        { product: '천호동원룸', price: 60, 신고수: 0},
        { product: '마포구원룸', price: 50, 신고수: 0},
      ],
      메뉴들 : ['Home', 'Shop', 'About'],
    }
  },
  methods: {
    increase(i) {
      this.rooms[i].신고수 += 1;
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
</style>
